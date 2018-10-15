pipeline {
    agent any

    environment {
        GLOBAL_ENV_VAR = 'this is a global environment variable'
    }

    stages {
        stage('build') {
            environment {
                STAGE_ENV_VAR = 'this is a stage environment variable'
            }
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
        stage('Test') {
            steps {
                echo 'test complete'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy complete'
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