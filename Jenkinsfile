pipeline {

  stage('Build a gradle project') {
                    // from the git plugin
                    // https://www.jenkins.io/doc/pipeline/steps/git/
                    git 'https://github.com/ezeadam123/Continuous-Delivery-with-Docker-and-Jenkins-Second-Edition.git'
                    sh '''
                    cd Chapter08/sample1
                    chmod +x gradlew
                    ./gradlew test
                    '''
                }

                stage("Code coverage") {

                    when { branch "main" }
                    steps { 

                        echo "This is the main branch"
                        sh '''
        	               pwd
               		cd Chapter08/sample1
                	    ./gradlew jacocoTestCoverageVerification
                        ./gradlew jacocoTestReport
                        '''
                    }                      
                }
}
