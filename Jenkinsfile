pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    echo "Клонируем репозиторий..."
                }
            }
        }
        stage ('Deploy with Ansible') {
            steps{
                sh 'docker exec ansible ansible-playbook /ansible/playbooks/test.yml --extra-vars "build_number=${BUILD_NUMBER}"'
            }
        }
    }
}