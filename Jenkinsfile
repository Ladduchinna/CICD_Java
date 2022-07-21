pipeline{
    agent any
    stages{
        stage("sonarqube quality check"){
            agent{
                docker{
                    image 'openjdk:8'
                }    
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar.token') { 
                        sh 'chmod +X gradlew'
                        sh './gradlew sonarqube'}
                }
            }
        }
    }
}
