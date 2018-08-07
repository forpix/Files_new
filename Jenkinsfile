#!/usr/bin/env groovy
/*
 *    This reflects commentary at https://wilsonmar.github.io/jenkins2-pipeline/
 *    This for comments only
 */
import hudson.model.*
import hudson.EnvVars
import groovy.json.JsonSlurperClassic
import groovy.json.JsonBuilder
import groovy.json.JsonOutput
import java.net.URL

def getRepoURL() {
 sh "git config --get remote.origin.url>.git/remote-url"
    return readFile (".git/remote-url").trim
}

node {
    stage ('\u2781 Stage') {
    echo 'checkout'
    git url: "https://github.com/forpix/Files_new.git"  
    echo "new way for commit:"
    }
   stage ('\u2782 Stage') {
   echo 'branch'
   echo "all new here"
   def scmVars=checkout scm
   echo 'scm : the commit id is ' +scmVars.GIT_COMMIT
   echo 'scm : the commit branch  is ' +scmVars.GIT_BRANCH
   echo 'scm : the previous commit id is ' +scmVars.GIT_PREVIOUS_COMMIT
   }
   stage ('\u2782 Stage') {
  git credentialsId: 'c536ecaa-ab06-459f-8dfb-03e78f6689a1', url: 'https://github.com/forpix/Files_new.git'
   sh '''
   git checkout Temp
   git merge -X theirs origin/master
   git remote set-url origin "https://forpix:mdali%40786@ggithub.com/forpix/Files_new.git"
   git push -u origin Temp
   echo "merged to the Temp branch has been done"
   '''
   }
   post {
   success {
           mail to: "mahammad.ali01@sap.com", subject:"success: ${currentBuild.fullDisplayName}", body: "Boo, we successed.https://github.wdf.sap.corp/c5271915/Testing.git"
        }
   failure {
            echo 'Your job is failed  "${currentBuild.fullDisplayName}" '
        }
 }
}
