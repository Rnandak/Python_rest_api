pipeline {
  agent any
  environment {
  dockerhome = tool 'mydocker'
  }
    stages{
      stage('Test version'){
        steps{
          sh 'python3 --version'
					echo "$env.build_number"
					echo "$env.build_id"
					echo "$env.build_tag"

        }
      }
     stage('Build Docker Image'){
       steps{
      sh "docker build -t rnandak/hello-world-python:0.0.2.RELEASE ."
				//script {dockerimage =docker.build("rnandak/hello-world-python-rest-api:${env.build_tag}")}

      }
      }
      stage('Docker Image Push'){
       steps{
        sh "docker push rnandak/hello-world-python:0.0.2.RELEASE"
      }
      }
    }
}
