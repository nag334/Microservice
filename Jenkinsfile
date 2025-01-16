pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://81C4FE5677A96A151554BA2723E6AED1.gr7.ap-south-1.eks.amazonaws.com']]) {
                        sh 'kubectl apply -f deployment-service.yml'
                        sleep 60
}
            }
        }
        
        stage('Verify Deployment') {
            steps {
                 withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://81C4FE5677A96A151554BA2723E6AED1.gr7.ap-south-1.eks.amazonaws.com']]) {
                        sh 'kubectl get all -n webapps'
                        
}
                
            }
        }
    }
}
