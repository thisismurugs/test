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
				withMaven(maven: 'local_maven', mavenSettingsConfig: 'f4b55deb-9e5b-47fb-9da2-64c98aeb3de0') {
					bat 'mvn -Dmaven.test.failure.ignore=true install'
				}
            }
        }
    }
}