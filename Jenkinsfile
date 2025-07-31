pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/Sirisha015/simple-devops-pipeline.git'
      }
    }
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t devops-demo .'
      }
    }
    stage('Run Container') {
      steps {
        sh 'docker rm -f devops-demo || true'
        sh 'docker run -d -p 80:80 --name devops-demo devops-demo'
      }
    }
  }
}
