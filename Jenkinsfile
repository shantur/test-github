def set_job_properties() {
  properties([
        pipelineTriggers([
          [
            $class: 'org.jenkinsci.plugins.ghprb.GhprbTrigger',
            cron: '',
            msgSuccess: 'Passed',
            msgFailure: 'Failed',
            whiteListLabels: 'build',
       	    triggerPhrase: 'ReBuild',
       	    onlyTriggerPhrase: true,
       	    useGitHubHooks: true,
       	    autoCloseFailedPullRequests: false,
    	    commitStatusContext: '',
         	gitHubAuthId: 'b3dd83ad-b4c6-4017-a15c-fe313bccb8a8'
          ]
      ]),
	[
		$class: 'GithubProjectProperty', 
		displayName: '', 
		projectUrlStr: 'https://github.com/shantur/test-ghprb'
		projectUrl: 'https://github.com/shantur/test-ghprb'
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
