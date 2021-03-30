pipeline{
        agent any
        stages{
            stage('Clone'){
                steps{
                    git clone https://github.com/raihan1995/jenkins-pipeline
                    
                }
            }
            stage('Install Docker & Compose'){
                steps{
                    sh "sudo docker-compose build"
                    sh "sudo docker-compose push"
                }
            }
             stage('Deploy'){
                steps{
                    sh "sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d"
                }
            }
        }    
}
