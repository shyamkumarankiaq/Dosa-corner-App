pipeline {
    agent {
        label 'linux-agent'
    }

    stages {

        stage('Hello World') {
            steps {
                echo 'Hello World from Jenkins Pipeline!'
            }
        }

        stage('Build') {
            steps {
                echo 'Starting Build...'
                sh 'echo "Build completed successfully - Poll SCM Test"'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh 'echo "All tests passed successfully"'
            }
        }

        stage('Create Artifact') {
            steps {
                echo 'Creating Build Artifact...'
                sh 'echo "Jenkins artifact created successfully" > build-artifact.txt'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'build-artifact.txt', fingerprint: true
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
