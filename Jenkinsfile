pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Checkout') {
            steps{
                git branch: 'master', credentialsId: 'd2e52a6d-2c83-46b7-97f3-8f19675bd4d2', url: 'git@github.com:vk1391/filebeat-role.git'
            }
        }
        stage('Install molecule') {
            steps{
                sh 'pip3 install -r test-requirements.txt'
            }
        }
        stage('Run Molecule'){
            steps{
                sh 'molecule test'
            }
        }
    }
}
