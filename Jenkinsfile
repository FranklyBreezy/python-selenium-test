pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/FranklyBreezy/python-selenium-test.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run Selenium Tests') {
            steps {
                sh 'pytest --maxfail=1 --disable-warnings -q'
            }
        }
    }
}
