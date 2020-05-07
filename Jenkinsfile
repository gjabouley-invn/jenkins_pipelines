pipeline {
    agent { label 'generic' }
    stages {
        stage('Build') {
            options { checkoutToSubdirectory('sources') }
            steps {
                checkout scm
                bat '''
                set
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Nothing to test yet'
            }
        }
        stage('Release') {
            // when { buildingTag() }
            options { checkoutToSubdirectory('script') }
            steps {
                echo 'Releasing ASIC ${GIT_BRANCH} / ${PARAMETER} / ${GIT_COMMIT}'
                git url: 'git@github.com:InvenSenseInc/sweng.chirpmicro-ihex2source',
                    branch: 'master',
                    credentialsId: 'scm-jenkins-github-ssh',
                    poll: false
                bat '''
                set
                '''
            }
        }
    }
}

