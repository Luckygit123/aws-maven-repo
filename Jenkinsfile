pipeline {
    agent any 
    stages {
        stage('clone repo and clean it') { 
            steps {
                sh "mvn clean "
                
            }
        }
        stage('Test') { 
            steps {
                sh "mvn test" 
            }
        }
        stage('Deploy') { 
            steps {
                sh "mvn package" 
            }
        }
		stage('image build') { 
            steps {
                sh "docker images"
                sh "docker build -t myjavaimage ."
                sh "docker login -u luckdockerdevops -p Lucky@123"
                sh "docker push luckdockerdevops/myjavaimage:latest"

    		}
    	}
    }
}
