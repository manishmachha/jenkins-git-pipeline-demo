pipeline {
    agent none
    stages {
        stage('non parallel') {
            agent {
                label 'master';
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
                            label 'master';
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
