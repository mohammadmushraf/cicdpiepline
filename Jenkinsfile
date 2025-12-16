pipeline {
    agent any

    stages {
        stage('Run Nginx Docker Container') {
            steps {
                sh '''
                docker rm -f nginx-static || true

                docker run -d \
                  --name nginx-static \
                  -p 80:80 \
                  -v $(pwd)/index.html:/usr/share/nginx/html/index.html \
                  nginx:latest
                '''
            }
        }
    }
}
