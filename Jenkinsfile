pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main',url: 'https://github.com/kenkool23/terraform-resource.git'
            }
        }
        
        stage('Init Terraform') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Manual Approval') {
            steps {
                input message: 'Apply Terraform?', ok: 'Yes'
            }
        }
         
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }

    }
}