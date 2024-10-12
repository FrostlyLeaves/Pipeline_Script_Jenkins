pipeline{
    agent none
    stages {
        stage('Non-Parallel Stage'){
            agent {
                label "built-in"
            }
            steps {
                echo "Excuted first!";
            }
        }
        
        stage('Run_Tests') {
            parallel {
                stage('Test On EHarddrive') {
                    agent {
                        label "External_Harddrive_Agent"
                    }
                    steps {
                        echo "Task1 on Agent";
                    }
                }
        
                stage('Test On Master') {
                    agent {
                        label "built-in"
                    }
                    steps {
                        echo "Task1 on Master";
                    }
                }
            }
	}			
    }
}
