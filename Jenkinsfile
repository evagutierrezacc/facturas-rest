pipeline {

    agent any
    stages{

        stage ("Descargar el codigo de la aplicacion"){

            steps{
                git "url"
            }
        }
        
        stage("Creación de imagen"){

            steps{

            bat "docker buil -t evagutierrez/app1 ."
        }
        }

        stage ("Ejecución de contenedor"){
           
           steps{ 
               bat "docker run -d --name app1 -p 8080:8080 evagutierrez/app1"

            }
        }

         stage ("Cerrar recursos"){
           
            steps {
                bat "docker stop app1"
                bat "docker container rm app1"
                bat "docker image rm evagutierrez/app1"

            }

        }

        }
    }