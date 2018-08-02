#!/groovy
import groovy.transform.Field

node('master') {

stage 'basic info'
def currentDir = pwd()
def comitId =  echo '${GIT_BRANCH}'
echo "-- pwd: $currentDir"
echo "-- workspace: ${env.WORKSPACE}"
echo "--the commit id is: $comitId "
echo "--the commited id is : ${env.GIT_BRANCH}"
echo "The ${env.JOB_NAME} job has begin on"
sh "ls"
echo "the commit id is ${env.GIT_COMMIT} "	
}
