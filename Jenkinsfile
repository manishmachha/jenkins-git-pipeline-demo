pipeline {
    agent none
    stages {
        stage('non parallel') {
            agent {
                label 'Node1';
            }
            steps {
                echo 'Hello %time%';
            }
        }
            stage('Parallel') {
                parallel {
                    stage('test on Node1') {
                        agent {
                            label 'Node1';
                        }
                        steps {
                            echo 'Building';
                            bat 'Hello.bat';
                        }
                    }
                    stage('Unit') {
                        agent {
                            label 'Node1';
                        }
                        steps {
                            echo 'Testing';
                            bat 'Test.bat';
                        }
                    }
                }
            }
    }
}
