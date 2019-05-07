pipeline {
    agent {
        label "jenkins-maven"
    }
    environment {
        DEPLOY_NAMESPACE = "jx-staging"
    }
    stages {
        stage('Top stage') {
            environment {
                A = "a"
                B = "b"
            }
            stages {
                stage('Second-level stage 1') {
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
                }
                stage('Second-level stage 2') {
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
    }
}
