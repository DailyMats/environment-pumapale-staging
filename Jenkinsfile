pipeline {
    agent {
        label "jenkins-maven"
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
                    sh 'git checkout -b ${BRANCH_NAME}-${BUILD_NUMBER}__sanitizer-basic'
                    sh 'git push origin ${BRANCH_NAME}-${BUILD_NUMBER}__sanitizer-basic'
                }
            }
        }
    }
}
