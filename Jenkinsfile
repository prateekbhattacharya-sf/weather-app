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
                        sh def text = readFile file: "values.yaml"
                        text = text.replaceAll("%tag%", "v2")
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
