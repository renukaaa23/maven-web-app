pipeline {  

    agent any
        
    tools{
        maven "Maven-3.9.9"
    }
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }

        stage('K8S deploy') {
    steps {
        sh 'export KUBECONFIG=/var/lib/jenkins/.kube/config && kubectl apply -f k8s-deploy.yml'
    }
}

    }
}
