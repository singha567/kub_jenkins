pipeline{
    agent any
        stages{
            stage("k8s"){
                steps{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: 'kubernetes', namespace: 'default', serverUrl: 'https://8F5FD86C1C06DACF6D623E6AD8148224.gr7.eu-west-2.eks.amazonaws.com']]) 
                    {
                    sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'
                    sh 'chmod u+x ./kubectl'
                   
                    sh './kubectl create -f pod.yaml'
                    sh './kubectl get pods'
                    }
                }    
        }
    }
}
