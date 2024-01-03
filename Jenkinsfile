def credential = 'github-appserver'
def server = 'team3@103.127.132.63'
def directory = '/home/team3/literature-frontend'
def branch = 'main'
def service = 'frontend'
def image = 'rakhafe/frontend'

pipeline {
    agent any
    stages {
        stage('building application'){
            steps {
                sshagent([credential]) {
                    sh '''ssh -o StrictHostKeyChecking=no team3@103.127.132.63 << EOF 
                    cd /home/team3/literature-frontend
                    docker.build("rakhafe:${env.BUILD_ID}") .
                    exit
                    EOF'''
                }
            }
        }
    }
}