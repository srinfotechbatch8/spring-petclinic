pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'feature/2026.06.18', url: 'https://github.com/srinfotechbatch8/spring-petclinic.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Generated the Test Reports') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('Generated the Artifacts') {
            steps {
               archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
         stage('Deploy') {
            steps {
              echo 'deploy'
            }
        }
    }
}
