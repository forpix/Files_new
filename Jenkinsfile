pipeline {
    agent any
    stages {
        stage('\u2781 Build') {
            steps {
		    sh 'git fetch --all'
                 sh 'git name-rev --name-only HEAD > GIT_BRANCH'
		sh 'cat GIT_BRANCH'
		git_branch = readFile('GIT_BRANCH').trim()
		env.GIT_BRANCH = git_branch
            }
        }
		stage('\u2780 new age') {
		steps {
		echo  'the comit id "${commitSha}" '
	
		
		}
		}
    }
	}
