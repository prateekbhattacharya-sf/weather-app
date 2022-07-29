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
                      sh checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/register.git']]])
                      dir('public/values.yaml') {
                        sh "pwd"
                        sh "sudo yq -i '.accountingService.tag = 'v2''"
                        sh "sudo yq -i '.authService.tag = 'v2''"
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
