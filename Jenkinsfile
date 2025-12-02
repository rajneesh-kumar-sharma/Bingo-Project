pipeline{
    agent any
    stages {
        stage('checkout code'){
        steps {
            git branch: 'master', url: 'https://github.com/rajneesh-kumar-sharma/Bingo-Project.git'
    }
    } 
    stage('Install Dependencies') {
            steps {
                sh "npm install"
            }
        }
    }
}