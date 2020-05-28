#!/usr/bin/env groovy
@Library('jenkins-pipeline')
def utils = new com.acceleratedskillup.Util()
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
println env.JOB_NAME
println env.JOB_BASE_NAME
 stage("trigger"){
  Utils.triggerReleaseJob(repo, shortCommit, version)
 }
}

