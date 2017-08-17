def set_job_properties() {
  properties([
    [
      $class: 'BuildDiscarderProperty',
      strategy: [
        $class: 'BuildRotator',
        daysToKeep: 5,
        numToKeep: 10,
        artifactsDaysToKeep: 5,
        artifactsNumToKeep: 10
      ]
    ],
    [
      $class: 'org.jenkinsci.plugins.workflow.job.properties.PipelineTriggersJobProperty',
      triggers: [
        $class: 'org.jenkinsci.plugins.ghprb.GhprbTrigger',
        msgSuccess: 'Passed',
        msgFailure: 'Failed',
        whiteListLabels(['build'])
      ]
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
