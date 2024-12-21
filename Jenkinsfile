@Library('Shared')_
pipeline{
    agent any
    
    stages{
        stage("Code clone"){
            steps{
                bat "whoami"
            clone("https://github.com/Sachin01001/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
