pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }
        stage('Deploy to Apache') {
            steps {
                echo 'Deploying files to Apache server...'
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r * /var/www/html/
                sudo systemctl restart apache2
                '''
            }
        }
    }
}
