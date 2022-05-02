pipeline {
    agent {
        label 'Mac_Mini'
          }
    stages {

        stage('Build') {
        when { 
            anyOf { 
                branch 'PR-*'
                tag 'release-*' 
                }
            }

            steps {
                echo "Build"
            }
        }
        stage('Test') {
        when { 
            anyOf { 
                branch 'PR-*'
                tag 'release-*' 
                }
            }
            steps {
                echo 'Test'
            }
        }
        stage('Deploy to Tag') {
            when { 
                anyOf { 
                    tag 'release-*' 
                    }
                }
            steps {
                echo 'Deploying only because this commit is tagged...............'
                
            }
        }
        stage('Deploy to PR') {
            when { 
                anyOf { 
                    branch 'PR-*'
                    }
                }
            steps {
                echo 'Deploying only because this commit is tagged...................'
                
            }
        }

        stage('Deploy to Tag and PR') {
            when { 
                anyOf { 
                    branch 'PR-*'
                    tag 'release-*' 
                    }
                }
            steps {
                echo 'Deploying only because this commit is tagged......................'
                
            }
        }
    }
}
