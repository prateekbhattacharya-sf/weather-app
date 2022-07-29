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
                    sh "pwd"
                    sh "sudo snap install yq" 
                    dir('biz-book-helm') {
                      sh "pwd"
                      git branch: 'test', credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/register.git'
                      dir('public/values.yaml') {
                        sh "pwd"
                        sh "sudo vi -i '.accountingService.tag = 'v2''"
                        sh "sudo vi -i '.authService.tag = 'v2''"
                      sh "git add ."
                      sh "git commit - "updated-values.yaml""
                      sh "git push origin main"

                      }

                    }
                
                }
            }
        }
    }    
}
