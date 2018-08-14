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
    writeFile file: "output/disk.sh", text: "#!/bin/bash
date;
echo "uptime:"
uptime
echo "Currently connected:"
w
echo "--------------------"
echo "Last logins:"
last -a |head -3
echo "--------------------"
echo "Disk and memory usage:"
df -h | xargs | awk '{print "Free/total disk: " $11 " / " $9}'
free -m | xargs | awk '{print "Free/total memory: " $17 " / " $8 " MB"}'
echo "--------------------"
start_log=`head -1 /var/log/messages |cut -c 1-12`
oom=`grep -ci kill /var/log/messages`
echo -n "OOM errors since $start_log :" $oom
echo ""
echo "--------------------"
echo "Utilization and most expensive processes:"
top -b |head -3
echo
top -b |head -10 |tail -4
echo "--------------------"
echo "Open TCP ports:"
nmap -p- -T4 127.0.0.1
echo "--------------------"
echo "Current connections:"
ss -s
echo "--------------------"
echo "processes:"
ps auxf --width=200
echo "--------------------"
echo "vmstat:"
vmstat 1 5 "
        sh '''
cd $pwd/output; chmod +x disk.sh; ./disk.sh
'''
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
