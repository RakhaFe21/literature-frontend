pipeline {
    agent any
    environment{
        credential = 'github-appserver'
        server = 'team3@103.127.132.63'
        directory = '/home/team3/literature-frontend'
        branch = 'main'
        service = 'frontend'
        image = 'rakhafe/frontend'
    }
    stages {
        stage('building application'){
            steps {
                sshagent([credential]) {
                    sh '''ssh -o StrictHostKeyChecking=no ${server} << EOF 
                    cd ${directory}
                    docker build -t ${image}:latest .
                    exit
                    EOF'''
                }
            }
        }
    }
}