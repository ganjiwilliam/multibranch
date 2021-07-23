pipeline{
    agent any
    stages{
        stage('cleaning'){
                steps{
                bat 'type NUL > ..\\\\svn.txt' 
                }
            }
        stage('two'){
            steps{
                script{
               def a=checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ganjiwilliam/Demo_repository.git']]])
               withEnv(['VAR1=VALUE ONE',"GIT_URL=${a.GIT_URL}",'VAR2=VALUE TWO',"GIT_COMMIT=${a.GIT_COMMIT}"]){
                
                bat 'echo %GIT_URL% >>  ..\\\\svn.txt'
                bat 'echo %GIT_COMMIT% >>  ..\\\\svn.txt'
               }
               echo " GIT COMMIT : ${a.GIT_COMMIT}"
               echo " GIT URL : ${a.GIT_URL}"
                }
            }
        }
            
        
    }
}

