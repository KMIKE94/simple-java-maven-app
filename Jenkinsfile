pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                node { label 'master' }
            }
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Deliver') {
            agent {
                node { label 'master' }
            }
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
