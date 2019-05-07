pipeline {
    agent {
        label "jenkins-maven"
    }
    environment {
        DEPLOY_NAMESPACE = "jx-staging"
    }
    stages {
        stage('Validate Environment') {
            environment {
                A = "a"
                B = "b"
            }
            parallel {
                stage('A') {
                    steps {
                        timeout(15) {
                            container('maven') {
                                sh 'echo start A=$A'
                                sleep 2
                                sh 'echo end A=$A'
                            }
                        }
                    }
                }
                stage('B') {
                    steps {
                        timeout(15) {
                            container('maven') {
                                sh 'echo start B=$B'
                                sleep 1
                                sh 'echo end B=$B'
                            }
                        }
                    }
                }
            }
            steps {
                timeout(15) {
                    container('maven') {
                        sh 'echo After A B'
                    }
                }
            }
        }
    }
}
