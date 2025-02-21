pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Cloning the repository from GitHub
                git url:'https://github.com/Santhosh2010-ramesh/CI-CD-Pipeline-for-Java-Web-Application.git',branch:'main'
            }
        }

        stage('Build') {
            steps {
                // Compile and package the Java application using Maven
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Run unit tests using Maven
                sh 'mvn test'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                // Deploy the WAR file to Tomcat server using SCP
                sh 'scp target/java-webapp.war user@tomcat-server:/var/lib/tomcat/webapps/'
            }
        }
    }
}
