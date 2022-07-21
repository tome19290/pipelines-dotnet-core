pipeline {
    agent any

     environment {


        SONAR_IP = "54.226.50.200"
        SONAR_TOKEN = "sqp_4f4904db430aba9948fce759bbf9777998547c44"

    }

   
    stages {
        stage('Restore') {
            steps {

                sh "dotnet restore"

            }
        }

        stage('Build') {
            steps {
                
                sh "dotnet build"

            }
        }

        stage('Test') {
            steps {
                
                sh "dotnet test"

            }

        }

       
        stage('Package') {
            steps {
                
                sh "dotnet publish"

            }

            post {
                success {
                    archiveArtifacts artifacts: './bin/Debug/net6.0/**.dll', followSymlinks: false
       
                }
            }
        }

       
        
    }
}