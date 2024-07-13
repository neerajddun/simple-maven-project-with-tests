pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/neerajddun/simple-maven-project-with-tests.git', branch: 'master'
            }
        }
        
      // stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
       // }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
        failure {
            mail to: 'neerajbijalwan96@gmail.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something is wrong with ${env.BUILD_URL}"
        }
    }
}
