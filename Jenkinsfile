pipeline {
  agent any
  stages {
    stage('greeting') {
      steps {
        sh 'echo "hello world"'
      }
    }
    stage('build docker') {
      steps {
        sh 'docker build -t bhargavit/popcorn:$BUILD_NUMBER .'
      }
    }
    stage('docker push') {
      steps {
        sh '''docker login -u bhargavit -p $DOCKER_PASSWORD
docker push bhargavit/popcorn:$BUILD_NUMBER'''
      }
    }
  }
}