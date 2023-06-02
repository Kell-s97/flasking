pipeline {
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

    stage('Docker Build') {
      steps {
        sh 'docker build -t kells97/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u kells97 -p dckr_pat_t-pKLBjCmvNjya88UHwQ9NW5nPM'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push kells97/flask_app'
      }
    }

  }
}