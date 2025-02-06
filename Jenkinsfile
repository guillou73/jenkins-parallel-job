pipeline {
    agent any
    stages {
        stage('single run') {
            parallel {
                stage('Parallel Test 1') {
                    steps {
                        script {
                            def group1 = [:]
                            group1["Job01"] = {
                                echo "Job01"
                                sh "date -u"
                                build(job: 'job-test-01')
                            }
                            group1["Job02"] = {
                                echo "Job02"
                                sh "date -u"
                                build(job: 'job-test-02')
                            }
                            group1["Job03"] = {
                                echo "Job03"
                                sh "date -u"
                                build(job: 'job-test-03')
                            }
                            parallel group1  // Run parallel tasks
                        }
                    }
                }
            }
        }
    }
}
