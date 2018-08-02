#!/groovy
import groovy.transform.Field

node('master') {

  stage 'print some basic info'
  def currentDir = pwd()
  echo "-- pwd: $currentDir"
  echo "-- workspace: ${env.WORKSPACE}"
 echo "The ${env.JOB_NAME} job has begin on"

sh "ls"
	echo "the commit id is ${env.GIT_COMMIT} "
  stage 'say your name'
	echo "I am node ${env.GIT_BRANCH}"
}
