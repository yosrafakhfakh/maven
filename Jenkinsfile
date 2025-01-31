pipeline {
    agent any
    tools {
        jdk 'jdk'
    }
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64'
        PATH = "$JAVA_HOME/bin:$PATH"
    }
    stages {
        stage('Compile Stage') {
            steps {
                withMaven(maven: 'maven') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage('Testing Stage') {
            steps {
                withMaven(maven: 'maven') {
                    sh 'mvn test'
                }
            }
        }
        stage('Install Stage') {
            steps {
                withMaven(maven: 'maven') {
                    sh 'mvn install -Dmaven.test.skip=true'
                }
            }
        }
    }
}
