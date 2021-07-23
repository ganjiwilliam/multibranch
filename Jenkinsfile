pipeline{
    agent any
    stages{
        stage('two'){
            agent{
                node{
                    label 'mylabel'
                    
                }
            }
            steps{
                script{
               def a=checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ganjiwilliam/Demo_repository.git']]])
               withEnv(["GIT_URL=${a.GIT_URL}","GIT_COMMIT=${a.GIT_COMMIT}"]){
                
                bat 'type NUL > ..\\\\svn.txt' 
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
