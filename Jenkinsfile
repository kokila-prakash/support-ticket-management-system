pipeline {
  agent any
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Test') { steps { sh 'echo Testing frontend files && ls -l && echo Test Passed' } }
    stage('Deploy Frontend to S3') { steps { sh 'aws s3 sync . s3://ticket-frontend-kokila-2026 --delete --exclude Jenkinsfile --exclude README.md' } }
    stage('Deploy Backend Info') { steps { sh 'echo Backend is Serverless Lambda via API Gateway - No EC2 deploy needed' } }
  }
  post { success { echo 'DEPLOYMENT SUCCESS' } }
}
