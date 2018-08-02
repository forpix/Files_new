#!/groovy

node('master') {

  stage 'print some basic info'
  def currentDir = pwd()
  echo "-- pwd: $currentDir"
  echo "-- workspace: ${env.WORKSPACE}"
sh "ls"
	echo 'the commit id is"${GIT_COMMIT}" '
  stage 'say your name'
	echo 'I am node "${en.GIT_BRANCH}" '
}
