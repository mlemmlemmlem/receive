#!/usr/bin/env groovy
@Library('jenkins-pipeline')
def utils = new com.acceleratedskillup.Util()
utils.trigger = 'true' 
def repo = 'mlemmlemmlem/siai-rily'
def branch = 'master'
def version = 'v.1.1.1'
node("master"){
stage("checkout"){
 checkout scm
  }
def shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
println shortCommit
println env.GIT_COMMIT
println ("job name") 
println env.JOB_NAME
println ("job base name")
println env.JOB_BASE_NAME
println env.BRANCH_NAME
println env.CHANGE_TARGET
def listJobName = "${env.JOB_NAME}".split('/')
def jobName = listJobName[0] + '/' + listJobName[1]
println utils.trigger
echo "Job Name (excl. path): ${jobName}"
 stage("trigger"){
  utils.triggerReleaseJob(repo, branch, shortCommit, version)
 }
}

