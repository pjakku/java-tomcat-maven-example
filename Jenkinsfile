pipeline {
    agent any
    stages {
        stage('Git Commit') {
            steps {
                echo 'Commit message'
            }
        }
        stage('Integration') {
            steps {
                echo 'Clean Build'
               // bat 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
                //bat 'mvn test'
            }
        }
        stage('code') {
            steps {
                echo 'Code Coverage'
                //jacoco()
            }
        }
        //test
        stage('Deploy') {
            steps {
                echo '## TODO DEPLOYMENT ##'
            }
        }
    }
    
    post {
        always {
            echo 'JENKINS PIPELINE'
        }
        success {
            echo 'JENKINS PIPELINE SUCCESSFUL'
        }
        failure {
            echo 'JENKINS PIPELINE FAILED'
        }
        unstable {
            echo 'JENKINS PIPELINE WAS MARKED AS UNSTABLE'
        }
        changed {
            echo 'JENKINS PIPELINE STATUS HAS CHANGED SINCE LAST EXECUTION'
        }
    }
}
