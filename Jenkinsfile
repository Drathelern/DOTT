pipeline{
    agent any
    stages{
        stage('Validate'){
            steps{
                sh 'mvn validate'
            }
        }
        stage('Clean'){
            steps{
                sh 'mvn clean'
            }
        }
        stage('Unit Test'){
            steps{
                sh 'mvn Test'
            }
        }
    }
}
