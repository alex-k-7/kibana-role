pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Checkout'){
            steps {
                git branch: 'main', credentialsId: '8043bfc7-5ee2-42d2-9984-a49fda22d32e', url: 'git@github.com:alex-k-7/kibana-role.git'
            }
        }
        stage('Install molecule'){
            steps{
                sh 'pip3 install -r test-req.txt'
            }
        }    
        stage('Run molecule'){
            steps {
                sh 'molecule test'
            }
        }    
    }
}