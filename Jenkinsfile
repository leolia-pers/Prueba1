pipeline {
    agent any
    
    stages {
        stage("Etapa unica") {
            steps {
                sh "mvn compile"
                sh "mvn test-compile"
                sh "mvn test"
                sh "mvn package"
            }
            post {
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
                junit 'target/surefire-reports/*.xml'
                cleanWs deleteDirs: true, patterns: [[pattern: 'target', type: 'INCLUDE']]
            }
        }
    }
}