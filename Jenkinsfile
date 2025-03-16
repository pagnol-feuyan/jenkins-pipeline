pipeline{
    agent any
    stages{
        stage('codeScan'){
            steps{
                sh 'trivy --version'
                
            }
        }
        stage('dockerImageBuild'){
            steps{
                sh 'docker -v'
            }
        }
        stage('PushImage'){
            steps{
                sh 'docker ps'
            }
        }
    }
}