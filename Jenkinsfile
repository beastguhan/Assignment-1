pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/beastguhan/Assignment-1.git'

            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-devops-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f python-app || true
                docker run -d -p 5000:5000 --name python-app python-devops-app
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Build Successful"
        }
        failure {
            echo "❌ Build Failed"
        }
    }
}
