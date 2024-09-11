pipeline {
    agent any

    tools {
        maven 'Maven 3.x' // Ensure this matches the Maven name configured earlier
    }

    stages {
        stage('Compile') {
            steps {
                echo 'Compiling the project...'
                sh 'mvn compile'
            }
        }
        stage('Code Review') {
            steps {
                echo 'Performing code review...'
                // Assuming you have a code review tool like SonarQube
                // sh 'mvn sonar:sonar'
                // For demonstration, we'll just print a message
                echo 'Code review completed.'
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Running unit tests...'
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging the application...'
                sh 'mvn package'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Deployment steps (e.g., copy WAR to Tomcat)
                sh '''
                cp target/my-app.war /path/to/tomcat/webapps/
                '''
            }
        }
    }

    post {
        success {
            echo 'Build and deployment completed successfully.'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
