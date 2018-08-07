#!/groovy
import groovy.transform.Field
import hudson.model.*

node('master') {

 stage ('\u2773 basic info'){
def scmVars=checkout scm
echo 'scm : the commit id is ' +scmVars.GIT_COMMIT
echo 'scm : the commit branch  is ' +scmVars.GIT_BRANCH
echo 'scm : the previous commit id is ' +scmVars.GIT_PREVIOUS_COMMI
sh 'git branch -r --sort=-committerdate --format="%(HEAD)%(objectname:short)" > GIT_COMMIT'
def shortCommit = readFile('GIT_COMMIT').take(6)
echo "The ${env.JOB_NAME} job has begin on"
 }
 stage ('\u2777 for commit id'){
 echo "chek here"
  echo "added the github in mutli branch pipeline"
 }
 stage ('\u2781 for branch'){
 sh 'git branch -r --sort=-committerdate  --format="%(HEAD) %(refname:short)" > GIT_BRANCH'
def branchName = readFile('GIT_BRANCH')
 echo "${branchName}"
echo "Here we are checking the special function"
 def scmVars = checkout scm
 echo "let's new funtion for commit id"
def commitHash = scmVars.GIT_COMMIT
 echo "****checking the println func.******"
 println "${commitHash}"
 echo "****checking the println echo one.******"
 echo "${commitHash}"
 }
  stage ('\u2779 for') {
  echo "check"
  }
  stage ('\u2780 for') {
   echo "added the new line"
   cleanWs()
  }
}
