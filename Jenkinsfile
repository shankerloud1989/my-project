pipeline {
    agent any
            stages {
                    stage('One') {
                        steps {
                            echo "Welocme to Cloudnloud technologies"
                        }
                    }
                    stage('Two') {
                        steps {
                                input('Please confirm to proceed')
                        }
                    }
                    stage('Three') {
                           when {
                                    not {
                                        branch 'master'
                                    }
                           }
                           steps {
                                    echo "Let dig ore in pipeline"
                           }
                    stage('Four') {
                                    parallel {
                                        stage('Unit test') {
                                                            steps {
                                                                echo "Running the unit test"
                                                            }
                                        }
                                        stage('Integration test') {
                                                            agent {
                                                                    docker {
                                                                         reuseNode false
                                                                         image 'centos'
                                                                    }
                                                            }
                                                            steps {
                                                                echo 'Running the integration testimg'
                                                            }
                                        }
                                    }
                    }
            }
}
