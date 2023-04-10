/* groovylint-disable LineLength */
/* groovylint-disable-next-line LineLength */
/* groovylint-disable CompileStatic, DuplicateStringLiteral, NestedBlockDepth, UnusedVariable, VariableName, VariableTypeRequired */
pipeline {
    agent any
    environment {
        def git_branch = 'main'
        def git_url = 'https://github.com/avidere/Ansible_SSL.git'

    }
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: "${git_branch}", url: "${git_url}"
                    echo 'Git Checkout Completed'
                }
            }
        } 
        stage('Generate/Renew and copy SSL Certificate on server'){
            steps{
                /* groovylint-disable-next-line DuplicateListLiteral */
                script{
                  sh "  ansible-playbook ssl.yaml -i hosts "
                }
            }

        }
    }
}
