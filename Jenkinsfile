#!/usr/bin/env groovy
/*
 *    This for comment section only !
 *    
 */
import hudson.model.*
import hudson.EnvVars
import groovy.json.JsonSlurperClassic
import groovy.json.JsonBuilder
import groovy.json.JsonOutput
import java.net.URL
node {
    try { 
     cleanWs()
    stage ("\u2780 Stage") {
    echo "successfully checkout in to the Git Repo,\u270C "
    echo"\u2705 This is from 1 stage is completed"
      }
   stage ('\u2781 Stage') {
   def scmVars=checkout scm
   echo 'scm : the commit id is ' +scmVars.GIT_COMMIT
   echo 'scm : the commit branch  is ' +scmVars.GIT_BRANCH
   echo 'scm : the previous commit id is ' +scmVars.GIT_PREVIOUS_COMMIT
   echo "\u2705 this is from 2nd Stage, completed"
   }
   stage ('\u2782 Stage') { 
   echo "we are in third stage of the build"
   echo "\u2705 this is from 3rd Stage,Completed"
       post
   }
        echo '############ \u2705 This will run only if successful #############'
         sh "pwd;ls -a"
    } 
  catch (e) {
   echo '************* \u274C This will run only if failed and sending a mail \u2709 \u2709 ****************'
   echo "\u2709 sent a mail for failure"
   throw e
    }
}
