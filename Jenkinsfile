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
                echo "${env.GIT_COMMIT}"
 
            }
        }
		stage('\u2780 build') {
		steps {
		echo  'the comit id "${commitSha}" '
		echo "${env.GIT_COMMIT}"
		
		}
		}
    }
	}
