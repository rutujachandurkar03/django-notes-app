@Library('Shared')_
pipeline{
    agent any
    
    stages{
        stage("Code clone"){
            steps{
                
            clone("https://github.com/rutujachandurkar03/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            docker_build("notes-app","latest" ,"rutuja0307")
            }
        }
        stage("Push to DockerHub"){
            steps{
                docker_push("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                docker_compose()
            }
        }
        
    }
}
