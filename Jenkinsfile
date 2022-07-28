pipeline {
    agent any
    stages{
        stage('git-clone'){
            steps{
                git branch: 'test', credentialsId: 'ayushi', url: 'https://github.com/ayushi212001/weather-app.git'
            }
        }
        stage('git-push'){
            steps{
                git add .
                git commit -m "updated files"
                git push origin master
            }
        }
    } 
}
