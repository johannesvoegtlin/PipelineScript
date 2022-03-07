pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "GeneralNode"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "WindowsKnoten"
                    }
                    steps {
                        echo "Task1 on Windows Agent"
                    }
                    
                }
                stage('Test On General Node') {
                    agent {
                        label "GeneralNode"
                    }
                    steps {
						echo "Task1 on General Node"
					}
                }
            }
        }
    }
}
