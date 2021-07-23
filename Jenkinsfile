pipeline {
    agent any
    environment{
        SVN='https://www.youtube.com/'
    }
    stages {
        stage('Example') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                bat 'echo %SVN% >> ..\\\\svn.txt'
                
            }
        }
    }
