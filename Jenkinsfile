pipeline {
    agent any
    tools {
        maven "MAVEN"
    }
    
    stages {
        stage('Git_clone') {
            steps {
                git branch: 'main', url: 'https://github.com/vdbsrinivasarao/maven_project.git'
            }
        }
        stage('Build_with_maven') {
            steps {
                sh "mvn install"
              }
         
           }
         } 
     }
       
    
   
