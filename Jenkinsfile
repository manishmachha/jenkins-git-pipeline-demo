pipeline {
    agent none
    stages {
        stage('non parallel') {
            agent {
                label 'Built-In Node';
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
                            label 'Built-In Node';
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
