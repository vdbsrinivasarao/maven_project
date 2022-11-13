pipeline {
    agent any
    tools {
        maven "mvn"
    }
    environment {
        PATH = "/opt/apache-maven-3.8.6/bin/bash: $PATH"
    }

    stages {
        stage('Git_clone') {
            steps {
                git branch: 'main', url: 'https://github.com/vdbsrinivasarao/maven_project.git'
            }
        }
        stage('Build_with_maven') {
            steps {
                sh 'mvn clean install'
            }
            post{
                success{
                    echo "Archiving the Artifacts"
                    
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            } 
        }
       
    }
    }
