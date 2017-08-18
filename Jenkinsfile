def set_job_properties() {
  properties([
    [
        pipelineTriggers([
          [
            $class: 'org.jenkinsci.plugins.ghprb.GhprbTrigger',
            cron: '',
            msgSuccess: 'Passed',
            msgFailure: 'Failed',
            whiteListLabels: 'build',
       	    triggerPhrase: 'ReBuild',
       	    useGitHubHooks: true,
       	    autoCloseFailedPullRequests: false,
    	    commitStatusContext: '',
         	gitHubAuthId: '17822187-4c0e-4a23-9f46-b67c1fdca35c'
          ]
      ])
    ]
    // pipelineTriggers([
    //   [
    //     $class: 'org.jenkinsci.plugins.ghprb.GhprbTrigger',
    //     cron: '',
    //     triggerPhase: 'ReBuild',
    //     useGitHubHooks: true,
    //     autoCloseFailedPullRequests: true,
    //     msgSuccess: 'Passed',
    //     msgFailure: 'Failed',
    //     commitStatusContext: 'New Hello',
    //     gitHubAuthId: 'b7ab205a-1d7c-4d9f-a7f8-60f65fc437d0',
    //     whiteListTargetBranches: [
    //       $class: 'org.jenkinsci.plugins.ghprb.GhprbBranch',
    //       branch: 'master'  
    //     ]
    //   ]
    // ])
  ])
}
pipeline {
  agent {
    node {
      label 'master'
    }
  }
 
stages {
  stage('Prepare') {
    steps {
      script {
        def artifactDownloadURL = "hello"
        echo "${artifactDownloadURL}"
      }
      set_job_properties()
      echo "${BUILD_NUMBER}"
      sh "env"
    }
  }
}
  post {
    always {
      deleteDir()
    }
  }
}
