pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/gautamdevgrovers/jenkins-docker-demo.git'
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
                    docker.image('jenkins-demo-image').run('-d -p 8082:80')
                }
            }
        }
    }

    post {
        success {
            echo 'Deployed successfully on Docker!'
        }
    }
}
