pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/devops-demo.git'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh '''
                kubectl --kubeconfig=/var/jenkins_home/config config use-context docker-desktop
                helm upgrade --install demo-app ./demo-app -n dev
                '''
            }
        }
    }
}

