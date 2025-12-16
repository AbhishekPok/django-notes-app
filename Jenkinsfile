@Library("DjangoDemo") _
pipeline {
    agent {
        label "vinod"
    }
    stages {
        stage("code fetch") {
            steps {
                script {
                    codefetch("https://github.com/AbhishekPok/django-notes-app.git","main")
                }
            }
        }
        stage("edit the code") {
            steps {
                // echo "issue seen with database connectivity, docker file. resolveing it."
                // sh "chmod +x /home/ubuntu/replace.sh "
                // sh "/home/ubuntu/replace.sh"
                echo "changed the repo and made changes as per requirements. hence for now not needed"
            }
        }
        stage("build the code") {
            steps {
                script {
                    buildthecode("note-app","latest","abhishekp0khrel")
                }
            }
        }
        stage("push the image to dockerhub") {
            steps {
                script {
                    pushtheimagetodockerhub("note-app","latest","abhishekp0khrel")
                }
            }
        }
        stage("deploy the code") {
            steps {
                script {
                    deploythecode()
                }
            }
        }
    }
}
