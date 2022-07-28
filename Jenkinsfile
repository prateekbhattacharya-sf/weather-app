pipeline {
    agent any
    stages{
        stage('git-clone'){
            steps{
                git branch: 'test', credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/weather-app.git'
            }
        }
        stage('yaml-update'){
            steps{
                git branch: 'main', credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/register.git'
                
            }
        }
        stage('git-push'){
            steps{
                script{
                    sh "sudo snap install yq"
                    sh "yq -i '.authService.tag = "qwerty"' ./public/values.yaml"
                    sh "yq -i '.accountingService.tag = "qwerty"' ./public/values.yaml"
                    sh "git add ."
                    sh "git commit -m "updated values""
                    sh "git push origin main"
                    withCredentials([usernamePassword(credentialsId: 'ayushi', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
                        sh('git push https://${GIT_USERNAME}:${GIT_PASSWORD}@github.com/ayushi212001/register.git')
                    }
                }
            }
        }
    } 
}
