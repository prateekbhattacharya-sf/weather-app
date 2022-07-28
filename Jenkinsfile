pipeline {
    agent any
    stages{
        stage('git-clone'){
            steps{
                git branch: 'test', credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/weather-app.git'
            }
        }
        stage('helm-clone'){
            steps{
                script{
                    git branch: 'main', credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/register.git'
                    sh "cd public"
                    def text = readFile file: "values.yaml"
                       text = text.replaceAll("%tag%", "v2")
                    sh "git add . -m "Update app image tag to v2""
                    sh "git push origin main"

                }    
            }
        }
        
    }

} 

