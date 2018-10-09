pipeline {

    def props = readProperties file: './config/test.properties'

    agent any

    stages{
        /*
        stage('Build'){
            steps {
                sh 'mvn clean package'
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }

        stage('Run Container') {
            steps {
                sh "docker run -d -p 8686:8080 tomcatwebapp:${env.BUILD_ID}"
            }
        }*/

        stage('Notification') {
            steps {
                parrallel (
                    line : {
                        echo 'token: props.LineToken'
                    },
                    slack: {

                    }
                )
            }
        }
    }
}
