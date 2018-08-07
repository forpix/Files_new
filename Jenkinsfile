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


node {
    stage ('\u2780 Stage') 
    echo 'checkout'
    git url: "https://github.com/forpix/Files_new.git"  
    echo "new way for commit:"
    
   stage ('\u2781 Stage') 
   echo 'branch'
   echo "all new here"
   def scmVars=checkout scm
   echo 'scm : the commit id is ' +scmVars.GIT_COMMIT
   echo 'scm : the commit branch  is ' +scmVars.GIT_BRANCH
   echo 'scm : the previous commit id is ' +scmVars.GIT_PREVIOUS_COMMIT
   
   stage ('\u2782 Stage') 
  git credentialsId: 'c536ecaa-ab06-459f-8dfb-03e78f6689a1', url: 'https://github.com/forpix/Files_new.git'
   sh '''
   git checkout Temp
   echo "merged to the Temp branch has been done"
   '''
    mail to: "mahammad.ali01@sap.com", subject:"success: ${currentBuild.fullDisplayName}", body: "Boo, we successed.https://github.wdf.sap.corp/c5271915/Testing.git"
 }
