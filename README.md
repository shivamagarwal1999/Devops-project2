# Devops-project2

Problem Statement :

*Create a container image that has jenkins installed using Dockerfile. When we launch this image it should automatically start the jenkins service in the container.
*Create a chain of jobs which will help to fetch source code, start service, test service, notify the status and in case of failure it will have capability to launch new environment in less that a minute or may be in just 1 second.

Task Description :
To solve this problem we are going to build chain of jobs in the jenkins each job will have their particular task :

But before heading towards the task we have to build our workspace so using Dockerfile we will build our workspace in our Windows, Linux or Mac. It is may be inside VM.

Job1 : This job will continuously monitor github and as soon as found any commit it will fetch all the content in that repository and will store in the workSpace.

Job2 : This job will identify whether the uploaded files are of HTML or PHP and accordingly it will react to launch server of corresponding language. Ex. If code is of PHP, then jenkins should start the container that has PHP already installed.

Job3 : We will use this job for testing our application. This job will fail itself on failure of website. Which will help to trigger next job.

Job4 : If third job failed due to any reason it means that our website is also crashed so in this scenario we should notify our developer. So we will use python script in this job to sent email to the developer.

Job5 : It is not the part of chained jobs, This will a monitoring job which will see whether our workspace is doing well or not if found it failing it will immediately launch a new container with the same configuration.
