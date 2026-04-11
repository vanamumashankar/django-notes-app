@Library('myshared') _
pipeline{
    agent any
    stages{
        stage("Started"){
            steps{
                echo "started the CICD"
            }
        }    
        stage("Code clone"){
            steps{
                sh "whoami"
            github_clone("https://github.com/LondheShubham153/django-notes-app.git","main")
            }
        }
     stage("docker login"){
            steps{
            Docker_Login("dockerHubCred")
            }
        }
        stage("Code Build"){
            steps{
            builds("dockerHubCred", "notes")
            }
        }
        stage("Push to DockerHub"){
            steps{
                push("dockerHubCred","notes","latest")
            }
        }
        stage("Deploy"){
            steps{
                End()
            }
        }
    }}
