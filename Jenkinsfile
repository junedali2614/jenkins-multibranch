pipeline {
    agent none
    stages {
        stage('Trigger Downstream Job') {
            steps {
                script {
                    node() {
                        checkout scm
                        def gitUrl = sh(returnStdout: true, script: 'git config remote.origin.url').trim()
                        build job: 'downstream_job', propagate: true,
                        parameters: [
                            string(name: 'GIT_URL', value: gitUrl),
                            string(name: 'BRANCH_NAME', value: env.BRANCH_NAME)
                        ]
                    }
                }
            }
        }
    }
}
