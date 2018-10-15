pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                retry(3) {
                    bat 'echo retry up to 3 times'
                }
                timeout(time: 3, unit: 'MINUTES') {
                    bat 'echo try up to 3 minutes'
                }
                bat 'python --version'
            }
        }
    }
}