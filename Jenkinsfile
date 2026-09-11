pipeline {
    agent any

    stages {
        stage('Hello World') {
            steps {
                echo 'Hello World from Jenkins Pipeline!'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Build completed successfully"'
            }
        }

        stage('Create Artifact') {
            steps {
                sh 'echo "Jenkins artifact created successfully" > build-artifact.txt'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'build-artifact.txt', fingerprint: true
            echo 'Pipeline completed successfully!'
        }
    }
}
