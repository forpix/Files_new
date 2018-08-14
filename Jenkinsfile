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
    stage ('\u2780 Stage') {
    echo 'checkout'
    git url: "https://github.com/forpix/Files_new.git"  
    echo "new way for commit:"
}
   stage ('\u2781 Stage') {
   echo 'branch'
   sleep time:1, unit:"MINUTES"
   echo "all new here"
   def scmVars=checkout scm
   echo 'scm : the commit id is ' +scmVars.GIT_COMMIT
   echo 'scm : the commit branch  is ' +scmVars.GIT_BRANCH
   echo 'scm : the previous commit id is ' +scmVars.GIT_PREVIOUS_COMMIT
   }
   stage ('\u2782 Stage') {
  git credentialsId: 'c536ecaa-ab06-459f-8dfb-03e78f6689a1', url: 'https://github.com/forpix/Files_new.git'
   echo 'we are in last stage of the build'
   }
   stage ('\u2780 UserInput-Stage') {
    userInput = input(
        id: 'userInput', message: "Some important question?", 
        parameters: [booleanParam(defaultValue: false, description: 'really?', name: 'myValue')])
}

stage('optional: do magic') {
    if (userInput) {
       echo 'this stage is optional only'
        echo 'this is from optional stage'
    } else {
        echo 'this is from else condition,'
        sh 'pwd'
        currentBuild.result = "UNSTABLE"
    }
}
 }
