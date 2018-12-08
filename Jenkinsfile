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
                bat 'dir'
                bat 'mvn --version'
                echo 'Thanks for the option'
         
    }
    }
        stage('Deploy for production') {
            when {
                branch 'master'
            }
            steps {
               echo 'Hello, JDK'
                bat 'java -version'
            } 
        }
        
      }
      }
    
