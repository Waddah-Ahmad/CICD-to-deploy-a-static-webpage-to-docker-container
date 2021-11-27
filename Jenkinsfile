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
                sh 'ssh -o StrictHostKeyChecking=no waddah@192.168.56.52 "cd /home/waddah/miniproject/CICD-to-deploy-a-static-webpage-to-docker-container ;\
		mkdir from_jenkins "'
            }
        }
    }
}
