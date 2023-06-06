pipeline {
  
  environment {
    registry = "kell-s97/flask_app"
    registryCredentials = "docker"
    cluster_name = "skillstorm"
  }
  
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/Kell-s97/flasking.git', branch: 'main')
      }
    }
  
  }
}    