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
                }
            }
        }
    }    
}
