pipeline{
    agent any:
    stages {
        stage('Checkout') {
            steps {
               git credentialsId: 'github', url: 'https://github.com/manju9676/javaApp.git'
            }       
        }
        stage('SCM'){
            steps{
                sh 'ls'
            }
        }
    }
}
