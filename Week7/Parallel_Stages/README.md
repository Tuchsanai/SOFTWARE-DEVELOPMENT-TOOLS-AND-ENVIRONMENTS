# Parallel steps in a stage



```
pipeline {
    agent any
    stages {
        stage('pre -build') {
            steps {
                sh 'echo Pre-build'
            }
        }
        stage('build') {
            steps {
                sh 'echo Build in progress.'
            }
        }
        stage('Unit tests') {
            steps {
                sh 'echo Running unit tests'
            }
        }
        stage('deploy') {
            steps {
                sh 'echo Deploying build'
            }
        }
        stage('Regression tests') {
        
                parallel{
                        stage('chrome') {
                            steps {
                                sh 'echo Running E2E tests on chrome'
                            }
                        }
                        stage('firefox') {
                            steps {
                                sh 'echo Running E2E tests on chrome'
                            }
                        }
                        stage('safari') {
                            steps {
                                sh 'echo Running E2E tests on chrome'
                            }
                        }
                }
            
        }
        stage('Release to prod') {
            steps {
                sh 'echo Releasing to prod'
            }
        }
    }
 post {
        always {
            echo 'Cleanup after everything!'
        }
    }
}
```
