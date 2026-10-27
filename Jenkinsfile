
pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                bat 'if exist app.log del app.log'
                bat 'start "" /B cmd /c "node app.js > app.log 2>&1"'
                bat 'ping 127.0.0.1 -n 4 > nul'
                bat 'type app.log'
                bat 'findstr /C:"Server running on port 3000" app.log'
            }
        }
    }
