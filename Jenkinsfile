pipeline {
    agent any
    stages {
        stage("Stage 1") {
            steps {
                sh 'pwd'
                firefox
}
    }
    post {
        success {
            echo 'stage1 is successful '
        }
        failure {
            echo 'stage1 is faiure'
        }
    }
	stage("Stage 2") {
            steps {
                sh 'pwd'
}
    }
    }
    post { 
        success{ 
               echo 'build is successful'
        }   
        }
        
}
