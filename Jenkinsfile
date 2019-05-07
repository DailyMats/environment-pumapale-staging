pipeline {
    options {
        disableConcurrentBuilds()
    }
    agent {
        label "jenkins-maven"
    }
    environment {
        DEPLOY_NAMESPACE = "jx-staging"
    }
    stages {
        stage('Validate Environment') {
            steps {
                parallel {
                    container('maven') {
                        sh 'echo A'
                    }
                    container('maven') {
                        sh 'echo B'
                        /*
                        dir('env') {
                            sh 'jx step helm build'
                        }
                         */
                    }
                }
            }
        }
        /*
        stage('Update Environment') {
            when {
                branch 'master'
            }
            steps {
                container('maven') {
                    dir('env') {
                        sh 'jx step helm apply'
                    }
                }
            }
        }
         */
    }
}
