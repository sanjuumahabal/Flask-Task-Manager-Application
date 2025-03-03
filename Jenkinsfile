pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/sanjuumahabal/Flask-Task-Manager-Application.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest tests/'  // Make sure you have tests in a 'tests/' folder
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 5000:5000 flask-app'
            }
        }
    }
}
