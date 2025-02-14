pipeline {
    agent {
        docker {
            image 'node:16-buster-slim'
            args '--privileged -v /var/run/docker.sock:/var/run/docker.sock -p 3001:3001'
        }
    }
    environment {
        DOCKER_HOST = "unix:///var/run/docker.sock"
        NPM_CONFIG_CACHE = "/root/.npm"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/user/repo.git' // Ganti dengan repo Git kamu
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run') {
            steps {
                sh 'npm start &'
            }
        }
    }
}
