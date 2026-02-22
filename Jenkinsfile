pipeline {
    agent any

    stages {

        stage('Pull Latest Code') {
            steps {
                checkout scm
            }
        }

        stage('Stop Old App') {
            steps {
                sh '''
                pkill -f app.py || true
                '''
            }
        }

        stage('Start App') {
            steps {
                sh '''
                nohup python3 app.py > output.log 2>&1 &
                '''
            }
        }
    }
}
