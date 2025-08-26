pipline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage ('Test Ansible') {
            sh ```
                cd  /ansible
                ansible-playbook \
                    -i inventory \
                    playbooks/test.yml \
                    --extra-vars "build_number= ${BUILD_NUMBER}"
            ```
        }
    }
}