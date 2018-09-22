pipeline {
    agent any

    parameters {
        string(name: 'BUILD_ID', defaultValue: '1.0', description: 'tomcat build version')
    }

    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}
