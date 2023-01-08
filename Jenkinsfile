
pipeline {
    triggers {
  pollSCM('* * * * *')
    }
   agent any
    tools {
  maven 'M2_HOME'
}
    stages {

        stage("build & SonarQube analysis") {          
            steps {
                dir('./fastfood_backend/'){
                    withSonarQubeEnv('sonarqube') {
                        sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=Yn-Olvr_full-cicd-pipeline'
                        }
                }
            }
          }
    }
}
