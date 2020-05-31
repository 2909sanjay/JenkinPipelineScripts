pipeline{
    agent none
    stages{
        stage('Non-Parallel Stage'){
            agent{
                label 'master'
            }
            steps{
                echo 'This is Non-Parallel Stage'
            }
        }
        stage('Run Tests'){
            parallel{
                stage('Test on Windows'){
                    agent{
                        label 'Win_Node'
                    }
                    steps{
                        echo 'Parallel Task on Windows'
                    }
                }
                stage('Test on Master'){
                    agent{
                        label 'master'
                    }
                    steps{
                        echo 'Parallel Task on Master'
                    }
                }
            }
        }
    }
}
