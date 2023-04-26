pipeline{
    agent any

    /*tools {
         maven 'maven'
         jdk 'java'
    }*/

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/sreenivas449/java-hello-world-with-maven.git']]])
            }
        }
        stage('build'){
            steps{
                sh '#!/bin/bash'
                sh '''
                    export MAVEN_HOME=/usr/local/Cellar/maven/3.9.1
                    export PATH=$PATH:$MAVEN_HOME/bin
                    mvn --version
                    mvn clean package
                '''
            }
        }
    }
}
