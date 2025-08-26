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
                sh '''
                    cd  /ansible
                    ansible-playbook \
                        -i inventory \
                        playbooks/test.yml \
                        --extra-vars "build_number= ${BUILD_NUMBER}"
                '''
            }
        }
    }
}