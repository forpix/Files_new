pipeline {
    agent any
    stages {
        stage('\u2781 Build') {
            steps {
             sh '''
             git fetch --all
            
             '''
               script {
          def commitSha = sh(returnStdout: true, script: 'git rev-parse HEAD').trim()
          println("commitSha: ${commitSha}")                                       
        } 
                echo "${commitSha}"
              
            }
        }
		stage('\u2780 new age') {
		steps {
		echo  'the comit id "${commitSha}" '
	
		
		}
		}
    }
	}
