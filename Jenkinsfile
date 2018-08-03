#!/groovy
import groovy.transform.Field
import hudson.model.*

node('master') {

stage '\u2756 basic info'
 sh "git fetch --all"
sh 'git branch -r --sort=-committerdate --format="%(HEAD)%(objectname:short)" > GIT_COMMIT'
def shortCommit = readFile('GIT_COMMIT').take(6)
echo "The ${env.JOB_NAME} job has begin on"

stage '\u2756 for commit id'
 echo "${shortCommit}"
 
 stage '\u2756 for branch'
 sh 'git branch -r --sort=-committerdate  --format="%(HEAD) %(refname:short)" > GIT_BRANCH'
def branchName = readFile('GIT_BRANCH')
 echo "${branchName}"
 
echo "Here we are checking the special function"
 def scmVars = checkout scm
 echo "let's new funtion for commit id"
def commitHash = scmVars.GIT_COMMIT
 def commitBranch = scmVars.GIT_BRANCH
 echo "****checking the println func.******"
 println "${commitHash}"
 echo "**************branch check"
 echo " ${commitBranch}"
 echo "****checking the println echo one.******"
 echo "${commitHash}"

}
