pipeline {
    agent { label 'built-in' }
    stages {
        stage('Validate') {
            steps {
                sh """
                    set -e
                    test -f index.html
                    test -f styles.css
                    test -f app.js
                    test -f dishes.js
                    test -f hero.png
                    grep -q '245' dishes.js
                    echo 'DosaCorner validation passed - 245 dishes.'
                """
            }
        }
        stage('Package') {
            steps {
                sh 'rm -rf deploy && mkdir deploy && cp index.html styles.css app.js dishes.js hero.png deploy/ && echo "Package created successfully."'
            }
        }
        stage('Deploy') {
            steps {
                sh 'mkdir -p "$HOME/dosacorner-site" && rm -rf "$HOME/dosacorner-site"/* && cp -r deploy/. "$HOME/dosacorner-site/" && echo "Deployed to $HOME/dosacorner-site"'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'deploy/*', fingerprint: true
            echo 'DosaCorner deployment completed successfully!'
        }
    }
}
