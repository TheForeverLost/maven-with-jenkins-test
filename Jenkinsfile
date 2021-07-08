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
                    mvn versions:set-property -Dproperty=revision -DnewVersion=1.0.1
                    mvn package
                '''
            }
        }
    }
}