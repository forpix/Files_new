#!/groovy
import groovy.transform.Field
import hudson.model.*

node('master') {

stage '\u2756 basic info'
 sh "git fetch --all"
def currentDir = pwd()
echo "-- pwd: $currentDir"
sh 'git branch -r --sort=-committerdate --format="%(HEAD)%(objectname:short)" > GIT_COMMIT'
def shortCommit = readFile('GIT_COMMIT').take(6)
echo "-- workspace: ${env.WORKSPACE}"
echo "The ${env.JOB_NAME} job has begin on"
sh "ls"

stage '\u2756 for commit id'
 echo "${shortCommit}"
 
 stage '\u2756 for branch'
 sh 'git branch -r --sort=-committerdate  --format="%(HEAD) %(refname:short)" > GIT_BRANCH'
def branchName = readFile('GIT_BRANCH')
 echo "${branchName}"
  def env = build.getEnvironment()
def gitCommit = env['GIT_COMMIT']
 echo gitCommit
}
