pipeline {
    agent any

    stages {

        stage('Pull Code') {
            steps {
                checkout scm
            }
        }

        stage('Stop Old App') {
            steps {
                bat '''
                taskkill /F /IM python.exe >nul 2>&1 || exit 0
                '''
            }
        }

        stage('Start App') {
            steps {
                bat '''
                start /B python app.py > output.log 2>&1
                '''
            }
        }
    }
}
