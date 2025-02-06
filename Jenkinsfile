pipeline {
    agent any
    stages {
        stage('single run') {
            parallel {
                stage('Parallel Test 1') {
                    steps {
                        script {
                            def group1 = [:]
                            group1["test1"] = {
                                echo "test1"
                                sh "date -u"
                                build(job: 'test1')
                            }
                            group1["test2"] = {
                                echo "test2"
                                sh "date -u"
                                build(job: 'test2')
                            }
                            group1["test3"] = {
                                echo "test3"
                                sh "date -u"
                                build(job: 'test3')
                            }
                            parallel group1  // Run parallel tasks
                        }
                    }
                }
            }
        }
    }
}
