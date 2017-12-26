node ('label') {

// Get all Causes for the current build
def causes = currentBuild.rawBuild.getCauses()

// Get a specific Cause type (in this case the user who kicked off the build),
// if present.
def specificCause = currentBuild.rawBuild.getCause(hudson.model.Cause$UserIdCause)

//Log logRotator set to 20 and timeout set
    sh '''options {

            buildDiscarder(logRotator(numToKeepStr:\'20\'))

            timeout(time: 60, unit: \'MINUTES\')
        }'''

// Environment details
    sh '''environment {

            def server_ip_address_or_name = ""

        		def server_username_name = ""

        		def server_password = "" // there is a way to get this from jenkins please google.
        		def git_url = ""
        	  }'''



stage "checkout"
      checkout scm

stage "Build"
      "mvn install -Dmaven.test.failure.ignore=true"








}
