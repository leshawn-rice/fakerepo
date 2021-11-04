properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Launching build server virtual machine'
                ansiblePlaybook playbook: '/home/ld-admin/playbooks/test/playbook.yml'
                echo 'Building firmware'
            }
        }
        stage('Test') {
            steps {
                sh 'cat ./test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
