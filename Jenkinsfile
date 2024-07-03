pipeline {
    agent any
    stages {
        stage('build'){
           parallel {
            stage('build with OpenJDK 8') {
                steps {
                    echo "JAVA_HOME is: ${env.JAVA_HOME}, PATH is: ${env.PATH}"
                    sh '''
                    devkit --version
                    '''
                }
            }
            stage('build with BishengJDK 8') {
                environment {
                    JAVA_HOME="/var/lib/jenkins/jdk/bisheng-jdk1.8.0_352"
                    PATH="${env.JAVA_HOME}/bin:${env.PATH}"
                }
                steps {
                    checkout scm
                    echo "JAVA_HOME is: ${env.JAVA_HOME}, PATH is: ${env.PATH}"
                    sh '''
                    '''
                }
            }
        } 
        }
        
    }
}

