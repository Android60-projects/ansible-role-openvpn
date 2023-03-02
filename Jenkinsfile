pipeline {
    agent molecule-test
    options {
        skipStagesAfterUnstable()
    }

    environment {

    }

    stages {
        stage('Test'){
            agent { label 'molecule-test' }
            steps {
                script {
                    sh "ls"
                }
            }
        }
        post {
            success {
                updateGitlabCommitStatus name: 'Test', state: 'success'
            }
            failure {
                updateGitlabCommitStatus name: 'Test', state: 'failed'
            }
        } 
        }
    }
post {
    success {
        updateGitlabCommitStatus name: 'Pipeline', state: 'success'
    }
    failure {
        updateGitlabCommitStatus name: 'Pipeline', state: 'failed'
    }
} 

