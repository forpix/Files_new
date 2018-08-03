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
 
 
def branch = env.BRANCH_NAME
   sh 'echo $BRANCH_NAME'
 def commit = env.GIT_COMMIT
   sh 'echo $commit'
 def scmVars = checkout scm
def commitHash = scmVars.GIT_COMMIT
 echo "commitHash"
 
 
}
