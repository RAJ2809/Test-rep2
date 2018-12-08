#!groovy​
   
pipeline {
    agent any 
    stages {
    
    stage('Deliver for development') {
            when {
    expression {
        return env.BRANCH_NAME != 'master';
        }
    }
            steps {
                echo 'Hello, Maven'
                echo env.BRANCH_NAME
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
    
