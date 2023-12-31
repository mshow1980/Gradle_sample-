pipeline {
    agent any
    stages {
        stage("sonar quality check") {
            agent {
                docker {
                    imahe 'openjdk:11'
                }
            }
            stage("building gradlew"){
                steps {
                    withSonarQubeEnv(credentialsId: 'sonar') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'

                    }
                }
            }
        }
    }
}