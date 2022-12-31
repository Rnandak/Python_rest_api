pipeline {
  agent any
  environment {
  dockerhome = tool 'mydocker'
  }
    stages{
      stage('Test version'){
        steps{
          sh 'python3 --version'
        }
      }
      stage('Build Docker Image'){
       steps{
        script{ "docker build -t rnandak/hello-world-python:$env.build_id ."}
      }
      }
      stage('Docker Image Push'){
       steps{
        script{"docker push rnandak/hello-world-python:$env.build_id"}
      }
      }
    }
}
