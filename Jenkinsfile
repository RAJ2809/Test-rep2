#!groovy​



pipeline {
    agent any 
    stages {
       
  
    
    stage('Deliver for development') {
        

            when {
    expression {
        return env.GIT_BRANCH != 'origin/master';
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
        return env.GIT_BRANCH == 'origin/master';
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
    
