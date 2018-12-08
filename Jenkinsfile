#!groovy​
   
pipeline {
    agent any 
    stages {
    
    stage('Deliver for development') {
            when {
                branch 'develop'
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
            }
            steps {
               echo 'Hello, JDK'
                bat 'java -version'
                
        }
        
      }
      }
      }
