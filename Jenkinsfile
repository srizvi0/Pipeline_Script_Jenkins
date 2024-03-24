pipeline {
    agent any
    stages {
        stage('Git-Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/srizvi0/Pipeline_Script_Jenkins.git'
                echo 'Checkout Complete'
            }
        }
        stage('Build'){
            steps{
                bat 'Build.bat'        
                echo 'Build Complete!'
            }
        }
        stage('Unit-Test') {
            steps {
                bat 'Unit.bat'        
                echo 'Unit test passed Successfully!'
            }
        }
        stage('Quality-Gate') {
            steps {
                bat 'Quality.bat'
                echo 'Quality Gate passed successfully!!!'
            }
        }
         stage('Deploy') {
            steps {
                bat 'Deploy.bat'
                echo 'Deploy Completed'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if run is marked as unstable'
        }
        changed {
            echo 'This will run only if the state of pipeline has changed'
            echo 'For example, if pipeline was previously fail, but now success'
        }
    }
}
