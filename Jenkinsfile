#!/groovy
import groovy.transform.Field

node('master') {

stage 'basic info'
 sh "git fetch --all"
def currentDir = pwd()
def comitId =  sh '${GIT_COMMIT}'
echo "-- pwd: $currentDir"
echo "-- workspace: ${env.WORKSPACE}"
echo "--the commit id is: $comitId "
echo "--the commited id is : ${env.GIT_BRANCH}"
echo "The ${env.JOB_NAME} job has begin on"
echo "${GIT_COMMIT}"
sh "ls"
echo "the commit id is ${env.GIT_COMMIT} "	
stage 'lets check this too'
 def scmVars = checkout([$class: 'GitSCM', branches: [[name: '*/master'], [name: '*/Temp'], [name: '*/working']], 
 doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
 userRemoteConfigs: [[credentialsId: 'b7b976fe-d54a-4990-a311-9c6339c5541d', url: 'https://github.com/forpix/Files_new']]])
env.GIT_COMMIT = scmVars.GIT_COMMIT
env.GIT_BRANCH = scmVars.GIT_BRANCH
 
}
