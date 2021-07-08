pipeline {
    agent any
    tools { 
        maven 'Maven 3.6.2' 
        jdk 'jdk11' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('Build') {
            steps {
                echo 'This is a minimal pipeline.'
                sh '''
                    pwd
                    BUILD_VERSION=$(mvn help:evaluate -Dexpression=project.version | grep "^[[:digit:]]{1,3}\.[[:digit:]]{1,3}\.?[[:digit:]]{0,3}")'
                    echo $BUILD_VERSION
                    mvn versions:set-property -Dproperty=revision -DnewVersion=1.0.1
                    mvn package
                '''
            }
        }
    }
}