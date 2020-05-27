#!/usr/bin/env groovy
@Library('jenkins-pipeline')
def utils = new com.acceleratedskillup.Util()

node("master"){
stage("checkout"){
 checkout scm
  }
shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
println shortCommit
println env.GIT_COMMIT
println env.JOB_NAME
println env.JOB_BASE_NAME
}

