pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-node-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                  docker rm -f node-app || true
                  docker run -d -p 3000:3000 --name node-app jenkins-node-app
                '''
            }
        }
    }
}
