pipeline {
  agent any
  environment {
  dockerhome = tool 'mydocker'
  }

    stages{
      stage('build'){
        step{
        sh 'python3 --version'
        }
      }
      stage('Test'){
      step{
      echo "test Step"
      }
      }
      stage('Build Docker Image'){
      step{
      "docker build -t rnandak/hello-world-python:$env.build_id ."
      }
      }
      stage('Docker Image Push'){
      step {
      "docker push rnandak/hello-world-python:$env.build_id"
      }
      }


    }





}
