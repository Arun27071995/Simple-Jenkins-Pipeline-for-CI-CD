pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'docker build -t my-flask-app .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "No tests yet, skipping..."'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh '''
                if [ $(docker ps -q -f name=flask-app) ]; then
                    echo "Container already running. Restarting..."
                    docker restart flask-app
                else
                    echo "Starting new container..."
                    docker run -d -p 5000:5000 --name flask-app my-flask-app
                fi
                '''
            }
        }
    }
}

