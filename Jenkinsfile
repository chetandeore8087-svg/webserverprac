pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/chetandeore8087-svg/webserverprac.git'
            }
        }

        stage('Deploy to Web Server') {
            steps {
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'Webserver',
                            transfers: [
                                sshTransfer(
                                    sourceFiles: '**/*',
                                    excludes: '.git/**,Jenkinsfile',
                                    remoteDirectory: ''
                                )
                            ],
                            verbose: true
                        )
                    ]
                )
            }
        }
    }
}
