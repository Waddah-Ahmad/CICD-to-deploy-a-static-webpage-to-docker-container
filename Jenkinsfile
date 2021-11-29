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
                sh '''ssh -o StrictHostKeyChecking=no jenkins@192.168.56.52 "cd /home/waddah/miniproject/CICD-to-deploy-a-static-webpage-to-docker-container; \
                # docker container commands to stop
                sudo docker container stop web;\
                sudo docker container rm -f web;\
                # cloning the repo
                sudo git pull origin master ; \
                #start a new container witnin any update
                sudo docker build -f Dockerfile --tag page:0.0 . ; \
                sudo docker container run -it -d --name web -p 8080:80 page:0.0 "'''
            }
        }
    }
}
