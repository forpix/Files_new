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
    git url: "https://github.com/forpix/Files_new.git"  
    echo "we are in to First Stage:"
    sh "mkdir -p output"
    writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
    writeFile file: "output/uselessfile.md", text: "This file is useless, no need to archive it."
    stage "Archive build output"
    archiveArtifacts artifacts: 'output/*.txt', excludes: 'output/*.md'
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
 }
