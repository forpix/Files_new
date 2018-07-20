pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
             script {
          def commitSha = sh(returnStdout: true, script: 'git rev-parse HEAD').trim()
          println("commitSha: ${commitSha}")
          def branch = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
          println("BranchName: ${branch}")
          sh "git remote -v"
          sh 'git log -n 1 --skip 1 --pretty=format:"%H"'
      def scmVars = checkout scm
    def branchName = scmVars.GIT_BRANCH
                 echo "${BRANCH_NAME}"
                 echo "${GIT_COMMIT}"
        }
            }
        }
    }
}
