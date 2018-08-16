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
 	// Clean workspace before doing anything
    deleteDir()

    try {
        stage ('Clone') {
        	checkout scm
        }
        stage ('Build') {
        	sh "pwd"
		echo 'shell scripts to build project...'
		sh '''
		chmod +x pattern.sh
		./pattern.sh
		echo 'script is done here, now in to parallel steps'
		'''
        }
        stage ('Tests') {
	        parallel 'static': {
	            sh "ls"
		    echo '**** **** *** ** * scripts to run static tests...'
	        },
	        'unit': {
	            sh "ls -a"
		    echo '##### ### ## #  scripts to run unit tests...'
	        },
	        'integration': {
	            sh "date"
		    echo '&&&& &&& && & scripts to run integration tests...'
	        }
        }
      	stage ('Deploy') {
            sh "ls -a"
	    echo '++++ +++ ++ +  scripts to deploy to server...'
	    echo "My branch is: '${env.BRANCH_NAME}'"
	    post
      	}
    } catch (err) {
	  echo "#### ### ## #"
	  echo "**** *** ** *"
        currentBuild.result = 'UNSTABLE'
    }
}
