pipeline{
    agent any
    stages{
        stage('codeScan'){
            steps{
                sh 'trivy fs .  -o resutl.html'
                sh 'cat result.html'
                
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