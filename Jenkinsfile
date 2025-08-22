pipeline {
    agent any
    stages {
        stage ('git clone'){
            steps {
                git branch: 'main', url: 'https://github.com/Sudhakar-FullStack-Developer/disneyhotstart.git'
            }
        }
        stage ('code compaile') {
            steps {
                sh'mvn compile'
            }
        }
        stage ('code test'){
            steps {
                sh 'mvn test'
            }
        }
        stage ('Generate Artifacts'){
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Depoy to Tomcat server'){
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'f201198f-f4ec-4d51-8fad-41bc64f237f5', path: '', url: 'http://13.201.59.131:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
