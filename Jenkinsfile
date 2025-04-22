@Library("Shared") _
pipeline{
    agent {label 'Hmm'}
    
    stages{
        stage('Heloo'){
            steps{
                script {
                    hi()
                }
            }
        }
        stage('Code'){
            steps{
                echo "This is cloning the code"
                script{
                clone("https://github.com/Jaryaldikshant/django-notes-app.git","main")
                }
            }
        }
        stage('Build'){
            steps{
                script{
                    docker_build("notes-app","latest","dikshant08")
                }
            }
        }
        stage('Push to DockerHub'){
            steps{
               script{
                   docker_push("notes-app","latest","dikshant08")
               }
            }
        }
        stage('Deploy'){
            steps{
                sh "docker compose up -d"
            }
        }
        
    }
}
