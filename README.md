# AWS_DevOps_Project
This is a simple web application utilising AWS DevOps tools.


### Technologies Used:
- Cloud9 (AWS IDE)
- CodeCommit, CodeArtifact, CodeBuild, CodeDeploy, CodePipeline
- S3
- EC2
- VPC
- CloudFormation (IAC)



### What are [AWS DevOps](https://aws.amazon.com/devops/) tools?
- CodeCommit:   A secure, highly scalable, fully managed source control service that hosts private Git repositories.
- CodeArtifact: Allows you to store artifacts using popular package managers and build tools and automatically fetches software packages on demand from public package repositories.
- CodeBuild:    A fully managed **continuous integration** service that compiles source code, runs tests, and produces ready-to-deploy software packages.
- CodeDeploy:   A fully managed **deployment** service that automates software deployments to various compute services
- CodePipeline: A fully managed **continuous delivery** service that helps you automate your release pipelines for fast and reliable application and infrastructure updates.


### Architecural Diagram (Created with [Draw.io](draw.io))
<div align=center margin= auto> 
  <img src="images/architecturaldiagram.png"  width=80%>
</div>


## 501st DevOps WebApp

**1) Setup Cloud9 IDE and install Java, Maven and other dependencies.**
<div align=center margin= auto> 
  <img src="images/1_1mvn_java_cloud9.png"  width=45%>
  <img src="images/1_2mvn-webapp-jsp.png" width="45%">
</div>

<br><br>

**2) Create CodeCommit repository and push initial commit.**
<div align=center margin= auto> 
  <img src="images/2_1codecommitgitrepo.png"  width=33%>
  <img src="images/2_2gitcloud9.png"  width=33%>
  <img src="images/2_3gittocodecommitpush.png"  width=33%>
</div>

<br><br>

**3) Create CodeArtifact Domain, repository, and create a settings.xml to connect the repository. Complie application with "mvn -s settings.xml compile" and CodeArtifact repository will display results.**
<div align=center margin= auto> 
  <img src="images/3_1Artifact_repositroypackagelow.png"  width=40%>
  <img src="images/3_2settingsxmlcodeartifact.png"  width=40%>
  </div>
<div align=center margin= auto> 
  <img src="images/3_3compiledpackageslocalrepocopyfrommvn.png"  width=60%>
</div>

<br><br>


**4) Create S3 Bucket to catch Build Artifact that gets created from build process with CodeBuild. It is stored there as a WAR (zip) file. Create CodeBuild Project and configure buildspec.yml to define the build commands and settings for building the application.**
<div align="center">
  <img src="images/4_2codebuild1.png" width="40%">
  <img src="images/4_3buidlspecyml.png" width="40%">
</div>

<div align="center">
  <img src="images/4_buildsuccessful.png" width="40%">
  <img src="images/4_zipfileaftersuccessfulbuild.png" width="40%">
</div>

<br><br>


**5) Implement IAC using CloudFormation to attempt to set up as much infrastrucutre as possible automatically. Delete exisitng resources first. Note that some Cloud Services can not be created with CloudFormation, in this case Cloud9.**
<div align="center">
  <img src="images/5_cloudformationscannedtemplate.png" width="50%">
  <img src="images/5_successfulcloudformationstack.png" width="50%">
</div>

<br><br>

**6) Implement CodePipeline to establish a CI/CD pipeline so you can automate execution of the above steps: Source, Build and Deploy.**
<div align="center">
  <img src="images/6_CodePipelinesuccessful.png" width="60%">
  <img src="images/6_hostedwebapponeEC2.png" width="60%">
</div>

<br><br>


### Architecural Diagram (Created with [Draw.io](draw.io))
<div align=center margin= auto> 
  <img src="images/architecturaldiagram.png"  width=80%>
</div>
