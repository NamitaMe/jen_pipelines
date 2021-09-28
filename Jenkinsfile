pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'javac Helloworld.java'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            //echo 'One way or another, I have finished'
            //deleteDir() /* clean up our workspace */
            //archiveArtifacts artifacts: '**/*.jar', fingerprint: true
            junit '**/build/test-reports/*.xml'
        }
        success {
            echo 'I succeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        
        changed {
            echo 'Things were different before...'
        }
    failure {
        echo 'Build failed.'
        /* mail to: 'namisur@yahoo.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}" */
    }
}

}
