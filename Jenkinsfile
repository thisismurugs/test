pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
				mvnHome = tool 'local_maven'
				def workspace = pwd()
				if (isUnix()) {
					sh "'${mvnHome}/bin/mvn' -N -B -f SOAHelloWorld/pom.xml -Denv=dev com.oracle.soa.plugin:oracle-soa-plugin:12.2.1-1-0:sar"
				} else {
					bat(/${mvnHome}\bin\mvn -e -X -N -f SOAHelloWorld -amd -pl com.muruga:SOAHelloWorld -Denv=dev com.oracle.soa.plugin:oracle-soa-plugin:12.2.1-1-0:sar/)
				}
            }
        }
    }
}