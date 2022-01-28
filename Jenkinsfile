pipeline {
    
    agent any
    
    stages {
        stage("Compilación") {
            
        }
        stage("Pruebas") {
            stages {
                stage("Pruebas Dinámicas") {
                    stages {
                        stage("Compilación pruebas") {
                            steps {
                                // Compilar pruebas -> Las pruebas no pueden ejecutarse
                            }
                        }
                        stage("Ejecución pruebas") {
                            steps {
                                // Ejecutar pruebas -> Genera informe... tanto si se ejecutan bien como si se ejecutan mal
                            }
                            post{
                                always {
                                    // Guardar el informe de pruebas <- 
                                }    
                            }
                        }
                    }
                }
               stage("SonarQube") {
                    // Sonarqube
                }
            }
        }
        stage("Empaquetado") {
            steps {
                // Empaquetar
            }
            post{
                success {
                    // Guardar el artefacto (resultante del empaquetado)
                }
            }
        }
    }
    post {
        always {
            // Borrar el espacio de trabajo
        }
    }
}
