pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'M398'
    }

    environment {
        JAVA_HOME = "${tool 'jdk17'}"
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Check Versions') {
            steps {
                sh 'echo $JAVA_HOME'
                sh 'java -version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
               // git branch: 'main', url: 'https://github.com/Vallabha-Devtools/jenkins-hello-world.git'
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
