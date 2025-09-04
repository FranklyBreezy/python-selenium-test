pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/YOUR_USERNAME/react-selenium-test.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Start App') {
            steps {
                script {
                    // Start app in background
                    sh 'nohup npm start &'
                    // Give time to start
                    sleep time: 15, unit: 'SECONDS'
                }
            }
        }
        stage('Run Selenium Tests') {
            steps {
                sh 'npm run test-selenium'
            }
        }
    }
}
