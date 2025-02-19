pipeline {
    agent any
    environment {
        NEXUS_URL = 'http://54.167.172.185:8081'  // Replace with your Nexus URL
        NEXUS_REPO = 'maven-releases'            // Replace with your Nexus Repository name
        NEXUS_CREDENTIALS_ID = 'nexus' // Jenkins credentials ID for Nexus
        ARTIFACT_NAME = 'javaApp.jar'            // Name of the artifact
    }
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github', url: 'https://github.com/manju9676/javaApp.git'
            }       
        }
        stage('SCM') {
            steps {
                sh 'ls'
            }
        }
        stage('Publish to Nexus') {
            steps {
                script {
                    sh """
                        curl -v -u admin:Manju208 --upload-file target/${ARTIFACT_NAME} \
                        ${NEXUS_URL}/repository/${NEXUS_REPO}/${ARTIFACT_NAME}
                    """
                }
            }
        }
    }

}
