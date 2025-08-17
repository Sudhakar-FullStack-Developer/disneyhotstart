pipeline {
    agent any
    stages {
        stage('git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/manojarinaresh/java_project_disneyhotstart.git'
            }
        }
        stage('code compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('code test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Generate Artifacts') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Depoy to Tomcat server') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '3adbb6de-7e97-4ce7-aee8-aa1d1fa4c3b6', path: '', url: 'http://13.127.99.117:8080')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
