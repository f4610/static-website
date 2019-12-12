pipeline {
    agent { docker { image 'node:6.3' } }
    stages {
        stage('build') {
            steps {
                sh 'npm install'
                sh 'npm install -g gatsby-cli'
                sh 'gatsby build'
            }
        }
         stage('test') {
            steps {
                sh 'npm install'
                sh 'npm install -g gatsby-cli'
                sh 'gatsby serve &'
                sh 'sleep 3'
                sh 'curl "http://localhost:9000" | tac | tac | grep -q "Gatsby"'
            }
        }
    }
}
