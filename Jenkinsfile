
 pipeline{
    agent any
    stages{
        stage('Checkout from Git'){
            steps{
                git branch: 'master', url: 'https://github.com/rajneesh-kumar-sharma/Bingo-Project.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh "npm install"
            }
        }
        stage('Run Tests') {
            steps {
                sh "npm test"
            }
        }
    }
}