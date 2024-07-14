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
                sh 'mvn verify -DskipUnitTests'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn clean install '
            }
        }
        

    }
}
