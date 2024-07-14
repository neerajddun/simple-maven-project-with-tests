pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/neerajddun/simple-maven-project-with-tests.git', branch: 'master'
            }
        }
        
        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('Integration Test') {
            steps {
                script {
                    catchError(buildResult: 'SUCCESS', stageResult: 'UNSTABLE') {
                        sh 'mvn verify -DskipTests=false -Pintegration-test'
                    }
                }
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn clean install '
            }
        }
        

    }
}
