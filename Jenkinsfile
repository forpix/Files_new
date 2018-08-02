pipeline {
    agent any
    stages {
        stage('\u2781 Build') {
            steps {
		    sh 'git fetch --all'
             sh 'git rev-parse HEAD > commit'
            def commit = readFile('commit').trim()
              echo "commit"
            }
        }
		stage('\u2780 new age') {
		steps {
		echo  'the comit id "${commitSha}" '
	
		
		}
		}
    }
	}
