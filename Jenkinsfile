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
        git(url: 'https://github.com/kell-s97/flasking.git', branch: 'main')
      }
    }
  
    stage('Build Stage') {
      steps {
        script {
          dockerImage = docker.build(registry)  
        }
      }
    }

    stage ('Deployment Stage') {
      steps{
        scripts{
          docker.withRegistry('', registryCredentials) {
            dockerImage.push()
          }
        }
      }
    }

  }
}    