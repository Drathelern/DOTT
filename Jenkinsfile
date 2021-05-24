pipeline {
  agent any
  stages {
    stage('Validate') {
      steps {
        sh 'mvn validate'
      }
    }

    stage('Clean') {
      steps {
        sh 'mvn clean'
      }
    }

    stage('Unite Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('SonarCloud') {
      steps {
        echo 'Sonar Cloud'
      }
    }

  }
  tools {
    maven 'Maven-3.8.1'
    jdk 'JDK11'
  }
}
