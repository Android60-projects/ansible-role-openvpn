pipeline {
    agent {
        node {
            label 'molecule-test'
        }
    }
    options {
        skipStagesAfterUnstable()
    }
    environment {
        PATH = "$HOME/.local/bin:$PATH"
    }

    stages {
        stage('Test'){
            agent { label 'molecule-test' }
            steps {
                script {
                    sh "whoami"
                    sh "pwd"
                    sh "echo $PATH"
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
}

