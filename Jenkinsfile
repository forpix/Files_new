pipeline {
    agent any
    stages {
        stage('\u2781 Build') {
            steps {
             sh '''
             git fetch --all
             a=$(git branch -r --sort=-committerdate --format='%(HEAD)%(objectname:short)'|awk '{print $1;exit}') 
             echo $a
             b=$(git branch -r --sort=-committerdate --format='%(HEAD)%(contents:subject)'|awk '{print $1}')
             echo $b
             c=$(git branch -r --sort=-committerdate --format='%(HEAD) %(refname:short)'|awk '{print $1;exit}')
             echo $c
             git remote -v
              echo "${GIT_BRANCH}"
                echo "${GIT_URL}"
                echo "$WORKSPACE{}"
              echo "the commit id is "${GIT_COMMIT}" "
              echo "${GIT_PREVIOUS_SUCCESSFUL_COMMIT}"
              script {
          def commitSha = sh(returnStdout: true, script: 'git rev-parse HEAD').trim()
          println("commitSha: ${commitSha}")
        } 
             '''
               echo "${commitSha}"
                echo "${env.GIT_COMMIT}"
        echo "a"
            }
        }
    }
}
