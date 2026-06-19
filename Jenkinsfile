node {

    stage('clone'){

        git branch: 'feature/2026.06.18', url: 'https://github.com/srinfotechbatch8/spring-petclinic.git'
    }

    stage('Build'){

        bat 'mvn clean install'
    }


    stage('Test'){

        bat 'mvn test'
    }

    stage('Generated Reports'){

        junit 'target/surefire-reports/*.xml'
    }

    stage('generated Artifacts'){

         archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
    stage('Deploy'){

        echo 'Deploy the project'
    }
}