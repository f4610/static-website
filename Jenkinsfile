pipeline {
  agent any
 
  tools {nodejs "node"}
 
  stages {
    stage('Example') {
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
