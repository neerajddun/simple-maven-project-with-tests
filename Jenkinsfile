pipeline {

  agent any 

  stages {

    stage ('git checkout') {

      steps {

        git 'https://github.com/neerajddun/simple-maven-project-with-tests.git'
      }
    }
stage ('Unit Test') {

      steps {

        sh 'mvn test'
      }
    }
    
    stage ('build') {

      steps {

        sh 'mvn clean install'
      }
    }
  }
}