pipeline {
    agent any
    tools { 
        maven 'local_maven' 
        jdk 'java10' 
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = %PATH%"
                    echo "M2_HOME = %M2_HOME%"
                ''' 
            }
        }

        stage ('Build') {
            steps {
                echo 'This is a minimal pipeline.'
				withMaven(maven: 'local_maven', mavenSettingsConfig: 'ae87e962-e481-43bd-96ff-22a9679c1b13',mavenLocalRepo: 'https://maven.oracle.com') {
					bat 'mvn -Dmaven.test.failure.ignore=true install'
				}
            }
        }
    }
}