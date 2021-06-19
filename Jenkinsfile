stage('branch1') {
            when { branch 'master' }
            environment {
                BRANCH_NAME = "${env.BRANCH_NAME}"
                ENV_NAME = "prod"
            }
            steps {
                sh "packer build jenkins/${PROJECT_NAME}/${PROJECT_NAME}-ami.json"
            }
        }
        stage('branch2') {
            when { branch 'development' }
            environment {
                BRANCH_NAME = "${env.BRANCH_NAME}"
                ENV_NAME = "dev"
            }
            steps {
                sh "packer build jenkins/${PROJECT_NAME}/${PROJECT_NAME}-ami.json"
            }
        }
        stage('branch3') {
            when { branch 'staging' }
            environment {
                BRANCH_NAME = "${env.BRANCH_NAME}"
                ENV_NAME = "staging"
            }
            steps {
                sh "packer build jenkins/${PROJECT_NAME}/${PROJECT_NAME}-ami.json"
            }
        }
