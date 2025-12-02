pipeline{
    agent any
    stages {
        stage('clean workspace'){ 
            steps {
                cleanWs()
            }
    }
        stage('checkout code'){
        steps {
            git branch: 'master', url: 'https://github.com/rajneesh-kumar-sharma/Bingo-Project.git'
    }
}
    }
}