#!/groovy
import groovy.transform.Field

node('master') {

stage 'basic info'
 sh "git fetch --all"
def currentDir = pwd()
def comitId =  echo '${GIT_COMMIT}'
echo "-- pwd: $currentDir"
echo "-- workspace: ${env.WORKSPACE}"
echo "--the commit id is: $comitId "
echo "--the commited id is : ${env.GIT_BRANCH}"
echo "The ${env.JOB_NAME} job has begin on"
  echo "${GIT_COMMIT}
sh "ls"
echo "the commit id is ${env.GIT_COMMIT} "	
}
