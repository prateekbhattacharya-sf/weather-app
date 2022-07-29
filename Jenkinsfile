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
                    sh "mkdir /var/lib/jenkins/workspace/test42/biz-book-helm"
                    sh "pwd"
                    sh "sudo snap install yq" 
                    dir('biz-book-helm') {
                      sh "pwd"
                      git branch: 'main', credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/register.git'
                      dir('public') {
                        yq -i '.accountingService.tag = 'v2'' values.yaml
                        yq -i '.authService.tag = 'v2'' values.yaml
                        sh "git add ."
                        sh "git commit - "updated-values.yaml""
                        sh "git push origin main"

                      }

                    }
                    sh "pwd"
                }
            }
        }
    }    
}
