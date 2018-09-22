pipeline {
    agent any

    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }

        stage('Run Container') {
            steps {
                sh "docker -d -p 8686:8080 tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}
