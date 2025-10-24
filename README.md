# jenkins-ansible-devops
jenkinsfile
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                git branch: 'main', url: 'https://github.com/aliyafarhat14-tech/jenkins-ansible-devops.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo Build process running...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo Test successful!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying using Ansible...'
                sh 'echo Ansible deployment here'
                // Example: sh 'ansible-playbook -i inventory deploy.yml'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}
