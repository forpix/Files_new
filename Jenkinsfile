pipeline {
    agent any
	define {
       def commit_id ="${GIT_COMMIT}"
     
     }
    stages {
        stage('\u2781 Build') {
            steps {
		   
		   
		   echo "${GIT_COMMIT}"
                  echo "${GIT_BRANCH}"
                 echo "${GIT_URL}"
                 echo "${GIT_PREVIOUS_COMMIT}"
               echo "${BUILD_ID}"
            }
        }
		stage('\u2780 new age') {
		steps {
		echo  'the comit id "${commitSha}" '
	echo $commit_id
		
		}
		}
    }
	}
