pipeline{
 	
 	agent { label 'maven' } // Es el agente que tiene Java 11 y Java 8

  	stages{
  		stage ('Build') {
  			steps {	
	  			sh './gradlew bootJAr --no-daemon'
	  		}
        }

        stage('Test') {
        	steps{
        		sh './gradlew test --no-daemon'
        		publishHTML([
        			reportDir: 'build/reports/tests/test',
        			reportFiles: 'index.html',
        			reportName: 'Tests Report',
        			keepAll: true,
					allowMissing: false, 
					alwaysLinkToLastBuild: false
        		])
        	}
        }

    }
}