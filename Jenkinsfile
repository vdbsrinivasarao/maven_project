pipeline {
    agent any
    
    tools {
        maven "mvn"
    }

    stages {
        stage('Git_clone') {
            steps {
                git branch: 'main', url: 'https://github.com/vdbsrinivasarao/maven_project.git'
            }
        }
        stage('Build_with_maven') {
            steps {
                sh 'mvn clean package'
            }
            post{
                success{
                    echo Ärchiving the Artifacts
                    
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            } 
        }
        stage ('deploy_to_container') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://54.218.134.45:8080')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
