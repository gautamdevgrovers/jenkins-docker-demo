pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/your-username/jenkins-docker-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('jenkins-demo-image')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d --name jenkins-demo-container -p 8082:80 jenkins-demo-image'
                }
            }
        }
    }

    post {
        success {
            echo 'Container should now be running on port 8082!'
        }
    }
}
