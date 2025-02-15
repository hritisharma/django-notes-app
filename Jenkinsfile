@Library("Shared") _
pipeline {
    agent { label "demo" }
    stages {
        stage("Start")
        {
            steps{
                script{
                    start()
                }
            }
        }
        stage("Code") {
            steps {
                script{
                    clone("https://github.com/LondheShubham153/django-notes-app.git","dev")
                }
                
            }
        }
        stage("Build") {
            steps {
                script{
                    dockerbuild("notes-app","latest","hritiksharma1612")
                }
            }
        }
        stage("Push to DockerHub") {
            steps {
                script{
                    dockerpush("notes-app","latest")
                }
            }
        }
        stage("Deploy") {
            steps {
               script{
                   deploy()
               }
            }
        }
    }
}

