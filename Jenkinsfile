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
                        container('maven') {
                            sh 'echo A=$A'
                        }
                    }
                }
                stage('B') {
                    steps {
                        container('maven') {
                            sh 'echo B=$B'
                        }
                    }
                }
            }
        }
    }
}
