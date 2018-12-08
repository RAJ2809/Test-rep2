#!groovy​



pipeline {
    agent any 
    stages {
       
        stage('Prepare') {
            steps {     
sh 'git name-rev --name-only HEAD > GIT_BRANCH'
sh 'cat GIT_BRANCH'
git_branch = readFile('GIT_BRANCH').trim()
env.GIT_BRANCH = git_branch
            }
        }
    
    stage('Deliver for development') {
        

            when {
    expression {
        return env.GIT_BRANCH != 'master';
        }
    }
            steps {
                echo 'Hello, Maven'
                echo env.GIT_BRANCH
                bat 'dir'
                bat 'mvn --version'
                echo 'Thanks for the option'
         
    }
    }
        stage('Deploy for production') {
            when {
                expression {
        return env.BRANCH_NAME == 'master';
        }
            }
            steps {
               echo env.BRANCH_NAME
               echo 'Hello, JDK'
                bat 'java -version'
            } 
        }
        
      }
      }
    
