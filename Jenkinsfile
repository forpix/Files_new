#!/groovy
import groovy.transform.Field
import hudson.model.*

node('master') {

stage '\u2756 basic info'
 def scmVars = checkout scm
def commitHash = scmVars.GIT_COMMIT
def commitBranch = scmVars.GIT_BRANCH

println  ' the commit id is "${commitHash }" '
println  ' the commited branch is "${commitBranch}" '

}
