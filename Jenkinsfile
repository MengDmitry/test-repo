pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage ('Test Ansible') {
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