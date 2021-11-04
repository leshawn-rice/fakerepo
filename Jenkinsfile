properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Launching build server virtual machine'
                ansiblePlaybook playbook: '/home/ld-admin/playbooks/test/playbook.yml'
                echo 'Building firmware'
            }
        }
        stage('Test') {
            steps {
                cat test
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
