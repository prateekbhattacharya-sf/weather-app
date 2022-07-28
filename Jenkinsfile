pipeline {
    agent any
    stages{
        stage('git-clone'){
            steps{
                git branch: 'jenkinsfile', credentialsId: 'ayushi', url: 'https://github.com/sourcefuse/biz-book-api.git'
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
