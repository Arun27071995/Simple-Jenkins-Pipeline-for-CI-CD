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
