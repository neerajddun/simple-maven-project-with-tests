pipeline {

  agent any 

  stages {

    stage ('git checkout') {

      steps {

        git 'https://github.com/neerajddun/simple-maven-project-with-tests.git'
      }
    }

    stage ('build') {

      steps {

        sh 'mvn clean install'
      }
    }
  }
}