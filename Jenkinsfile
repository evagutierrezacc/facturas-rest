pipeline {

    agent any
    stages{

        stage ("Descargar el codigo de la aplicacion"){

            steps{
                git "https://github.com/evagutierrezacc/facturas-rest.git"
            }
        }
        
        stage("Creación de imagen"){

            steps{

            bat "docker buil -t evagutierrez/facturas-node-16 ."
        }
        }

        stage ("Ejecución de contenedor"){
           
           steps{ 
               bat "docker run -d --name app-facturas-node -p 8080:8080 evagutierrez/facturas-node-16"

            }
        }

         stage ("Cerrar recursos"){
           
            steps {
                bat "docker stop app1"
                bat "docker container rm app-facturas-node"
                bat "docker image rm evagutierrez/facturas-node-16"

            }

        }

        }
    }