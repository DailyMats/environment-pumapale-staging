pipeline {
    agent {
        label "jenkins-maven"
    }
    environment {
        DEPLOY_NAMESPACE = "jx-staging"
    }
    stages {
        stage('Top stage') {
            steps {
                container('jx-base') {
                    sh 'jx get pipelines'
                }
            }
        }
    }
}
