// Sintaxis declarativa: MAS SENCILLA y LA MAS USADA. Menos potente que la de scripting... 
//          pero mucho MAS que los proyectos de estilo libre
// Sintaxis de scripting: MAS COMPLEJA Y MAS POTENTE: Puedo hacer lo que quiera con Jenkins
pipeline {
    
    agent any // Para definir DONDE QUIERO QUE SE EJECUTE ESTA TAREA
    
    stages {
       stage("Etapa 1") {
           steps { // Hacemos las llamadas a los plugins
               sh "echo Soy la etapa 1" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Salgo de la etapa 1" // Llamada al plugin que ejecuta una shell
           }
           post {
               always { // Post tareas que deben ejecutarse siempre
                  sh "echo Acabó la etapa 1" 
               }
               success { // Post tareas que SOLO se ejecutan si los pasos han finalizado correctamente
                  sh "echo Y acabó bien" 
               }
               failure { // Post tareas que SOLO se ejecutan si los pasos han dado error
                  sh "echo Pero acabó con error" 
               }
           }
       }
       stage("Etapa 2") {
           stages {
               stage("Etapa 2.1") {
                   steps {
                       sh """
                       echo Soy la etapa 2.1
                       echo Acabo la etapa 2.1
                       """
                   }
                   post {
                       always { // Post tareas que deben ejecutarse siempre
                          sh "echo Acabó la etapa 2.1" 
                       }
                       success { // Post tareas que SOLO se ejecutan si los pasos han finalizado correctamente
                          sh "echo Y acabó bien" 
                       }
                       failure { // Post tareas que SOLO se ejecutan si los pasos han dado error
                          sh "echo Pero acabó con error" 
                       }
                   }
               stage("Etapa 2.2") {
                   steps {
                       sh """
                       echo Soy la etapa 2.2
                       echo Acabo la etapa 2.2
                       """
                   }
                   post {
                       always { // Post tareas que deben ejecutarse siempre
                          sh "echo Acabó la etapa 2.2" 
                       }
                       success { // Post tareas que SOLO se ejecutan si los pasos han finalizado correctamente
                          sh "echo Y acabó bien" 
                       }
                       failure { // Post tareas que SOLO se ejecutan si los pasos han dado error
                          sh "echo Pero acabó con error" 
                       }
                   }
               }
           }
       }
    }
    }
   post {
       always { // Post tareas que deben ejecutarse siempre
          sh "echo Acabaron todas las etapas" 
       }
       success { // Post tareas que SOLO se ejecutan si los pasos han finalizado correctamente
          sh "echo Y acabó bien" 
       }
       failure { // Post tareas que SOLO se ejecutan si los pasos han dado error
          sh "echo Pero acabó con error" 
       }
   }

}