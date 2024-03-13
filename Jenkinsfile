pipeline {
    agent any
    
    tools {
        terraform 'jenkins-terraform'
    }
    stages {
        stage ("checkout from GIT") {
            steps {
                git branch: 'main', credentialsId: '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', url: 'https://github.com/Nikhilkumarr/CICD-pipeline/'
            }
        }//credentialsId: 'aa3e80aa-e369-421e-a28e-21c892e2e6da',
        stage ("terraform init") {
            steps {
                sh 'terraform init'
            }
        }
        stage ("terraform fmt") {
            steps {
                sh 'terraform fmt'
            }
        }
        stage ("terraform validate") {
            steps {
                sh 'terraform validate'
            }
        }
        stage ("terrafrom plan") {
            steps {
                sh 'terraform plan '
            }
        }
        stage ("terraform apply") {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
    }
}
