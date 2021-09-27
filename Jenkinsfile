pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "I am in main branch"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}
