pipeline {
    agent any 
    stages {
        stage('build ') { 
            steps {
                echo "this is build artifacts stage where we install all the depensences and packages for the environment"
            }
        }
        stage('Test') { 
            steps {
                echo "this is test stage where we debug the software before going further"
            }
        }
        stage('Deploy') { 
            steps {
                sh '''ssh -o StrictHostKeyChecking=no jenkins@192.168.56.52 "cd CICD-to-deploy-a-static-webpage-to-docker-container; \
                # docker container commands to stop
                sudo docker container stop web1:latest;\
                sudo docker container rm web1:latest;\
                sudo docker image rm -f web:latest;\
                # cloning the repo
                git clone https://github.com/Waddah-Ahmad/CICD-to-deploy-a-static-webpage-to-docker-container.git ; \
                #start a new container witnin any update
                sudo docker build -f Dockerfile --tag web:latest . ; \
                sudo docker container run -it -d --name page1 -p 8080:80 web1:latest "'''
            }
        }
    }
}
