pipeline {
    agent {
        label 'saltssh'
    }

    stages {
        stage('check minion version') {
            steps {
                script {
                    sh 'sudo salt "*" test.version'
                }
            }
        }
        stage('run uptodate') {
            steps {
                script {
                    sh 'cd /srv/salt'
                    sh 'sudo salt "*" state.apply uptodate'
                }
            }
        }
    }
}
