pipeline{
    agent any
    stages{
        stage('codeScan'){
            steps{
                sh 'trivy fs .  -o resutl.html'
                
            
                
            }
        }
        stage(dockerLogin){
            steps{
                sh 'aws ecr get-login-password --region us-east-1 | \
                docker login --username AWS \
                --password-stdin 390403862591.dkr.ecr.us-east-1.amazonaws.com'
            }
        }
        stage('dockerImageBuild'){
            steps{
                sh 'docker build -t jenkins-ci .'
            }
        }
        stage('dockerImageTag'){
            steps{
                sh 'docker tag jenkins-ci:latest 390403862591.dkr.ecr.us-east-1.amazonaws.com/jenkins-ci:latest'
            }
        }
        stage('PushImage'){
            steps{
                sh 'docker push 390403862591.dkr.ecr.us-east-1.amazonaws.com/jenkins-ci:v0.0.2'
            }
        }
    }
}