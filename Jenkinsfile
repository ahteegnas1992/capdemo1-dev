#!/usr/bin/env groovy 

/*
 * This file bootstraps the codified Continuous Delivery pipeline for extensions of SAP solutions such as SAP S/4HANA.
 * The pipeline helps you to deliver software changes quickly and in a reliable manner.
 * A suitable Jenkins instance is required to run the pipeline.
 * More information on getting started with Continuous Delivery can be found here: https://sap.github.io/jenkins-library/
 */

@Library('piper-lib-os') _

node(){
  stage('Prepare')   {
      deleteDir()
      checkout scm
      setupCommonPipelineEnvironment script:this
  }

  stage('Build')   {
      mtaBuild script:this
    
    //sh "mbt build --mtar cicd.mtar --platform CF --source ./ --target /var/jenkins_home/workspace/Cargill/cap_deployment"
    
  }

 // stage('Deploy')   {
 //     cloudFoundryDeploy script:this, deployTool:'mtaDeployPlugin'
 // }
}
