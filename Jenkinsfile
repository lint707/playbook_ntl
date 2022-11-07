pipeline {
    agent any

    stages {
        stage('Checkout STM') {
            steps {
                git branch: 'master', credentialsId: 'e840b753-6713-44d0-a1f3-6964d19b46b9', url: 'git@github.com:lint707/playbook_ntl.git'
            }
        }
        stage('Download molecule') {
            steps {
                sh 'pip3 install molecule molecule_docker'
            }
        }        
  
        stage('Molecule test') {
            steps {
                sh '''cd roles/clickhouse-role/
                molecule test -s centos_7'''
            }
        }        
        
    }
}
