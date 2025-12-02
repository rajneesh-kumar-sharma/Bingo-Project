
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
        stage("Docker Build & Push"){
            steps{
                withCredentials([usernamePassword(credentialsId:"dockerHub",passwordVariable:"DOCKERHUB_PASSWORD",usernameVariable:"DOCKERHUB_USERNAME")]){
        sh "docker build -t ${env.DOCKERHUB_USERNAME}/bingo ."
        sh "docker login -u ${env.DOCKERHUB_USERNAME} -p ${env.DOCKERHUB_PASSWORD}"
        sh "docker tag ${env.DOCKERHUB_USERNAME}/bingo ${env.DOCKERHUB_USERNAME}/bingo:latest"
        sh "docker push ${env.DOCKERHUB_USERNAME}/bingo"
                }
            }
        }
        stage("Deploy"){
            steps{
                sh "docker compose down && docker compose up -d"

            }
        }
    }
}