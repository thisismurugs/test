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
				withMaven(maven: 'local_maven', mavenSettingsConfig: 'MvnGlobalSettings') {
					bat 'mvn -Dmaven.test.failure.ignore=true install'
				}
            }
        }
    }
}