pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                retry(3) {
                    echo 'retry up to 3 times'
                }
                timeout(time: 3, unit: 'MINUTES') {
                    echo 'try up to 3 minutes'
                }
                bat 'python --version'
            }
        }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run is marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}