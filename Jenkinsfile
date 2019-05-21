pipeline {
    agent {
        label "jenkins-jx-base"
    }
    stages {
        stage('Trigger other builds') {
            when {
                not {
                    branch '*__sanitizer-*'
                }
            }
            steps {
                container('jx-base') {
                    //sh 'git checkout -b ${BRANCH_NAME}-${BUILD_NUMBER}__sanitizer-basic'
                    //sh 'git push origin ${BRANCH_NAME}-${BUILD_NUMBER}__sanitizer-basic'
                    sh 'Hello'
                }
            }
        }
    }
}
