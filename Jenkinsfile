pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/<YOUR_GITHUB_USERNAME>/cicdpipeline.git'
            }
        }

        stage('Deploy with Docker & Nginx') {
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

