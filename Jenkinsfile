#!/groovy
import groovy.transform.Field

node('master') {

stage 'basic info'
 sh "git fetch --all"
def currentDir = pwd()
echo "-- pwd: $currentDir"
sh 'git branch -r --sort=-committerdate --format="%(HEAD)%(objectname:short)" > GIT_COMMIT'
def shortCommit = readFile('GIT_COMMIT').take(6)

echo "-- workspace: ${env.WORKSPACE}"
echo "--the commited id is : ${env.GIT_BRANCH}"
echo "The ${env.JOB_NAME} job has begin on"
sh "ls"
echo "the commit id is ${env.GIT_COMMIT} "	
stage 'lets check this too'
 sh 'echo Branch Name: $BRANCH_NAME'
 echo "${shortCommit}"
 
}
