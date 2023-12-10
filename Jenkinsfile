pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build your Spring Boot application
                    sh './gradlew clean build'
                }
            }
        }

        stage('Deploy to OpenShift') {
            steps {
                script {
                    // Deploy to OpenShift using oc commands
                    sh 'oc login -u <username> -p <password> <openshift-cluster-url>'
                    sh 'oc project <project-name>'
                    sh 'oc apply -f openshift-deployment.yaml'
                }
            }
        }
    }
}
