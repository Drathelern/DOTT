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

    stage('Static Code analysis') {
            environment {
                scannerHome = tool 'SonarCloud'
            }
            steps {
                withSonarQubeEnv('SonarCloud') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
                timeout(time: 1, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
    }

  }
  tools {
    maven 'Maven-3.8.1'
    jdk 'JDK11'
  }
}
