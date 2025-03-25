## In this phase, we will build onto the previous "Terraform on AWS" project by integrating SonarCloud to scan a vulnerable application
### 1. Update the Jenkins file (Jenkinsfile)
<li>open the repo on github. this contains a vulverable web application</li>

![Image](https://github.com/user-attachments/assets/761d8c65-3f4d-4595-a9b4-62a4087f0660)
![Image](https://github.com/user-attachments/assets/648cbcf0-f451-4a88-8567-de8f2bc1a449)
<li>open the jenkins file. be sure the maven name matches the name used in jenkins. the code outlines the stages to run sonar analysis on the source code</li>

![Image](https://github.com/user-attachments/assets/217cf17d-b240-48e0-a166-9600e27e1d5a)
<li>we need to update the projectkey, organization, host url, and login token. all will be defined in sonarcloud.</li>
<li>click + to add an organization</li>

![Image](https://github.com/user-attachments/assets/b8fb7306-ce6f-4026-89f8-1a66c0e8590c)
<li>select create an organization manually. provide a name and key </li>

![Image](https://github.com/user-attachments/assets/d84e38f4-a580-4d07-a055-730dd58d4896)
<li>select free plan and create organization. select analyze a new project</li>

![Image](https://github.com/user-attachments/assets/53a24121-ba81-4223-95b8-3b716dbf4920)
<li>enter the org name and sonarcloud will provide a project key, and select public> next> previous version> create project</li>

![Image](https://github.com/user-attachments/assets/ae7c1a22-2d24-49a5-b03d-45107f4e6eab)
<li>go back to the jenkins file and change the organization and project key. verify host url is sonarcloud.io. now create the token on sonarcloud. at the top right> my account> security> generate token> provide token name and create generate token. copy the token and store an a notepad</li>

![Image](https://github.com/user-attachments/assets/b3b7877c-b7a0-450d-a486-7304145ddaa7)

![Image](https://github.com/user-attachments/assets/88d48d03-dfeb-41ef-9e97-18b609927d05)
<li>paste token into the jenkins file. commit the changes. now back to the jenkins dashboard: new item> provide a pipeline name> select pipeline. ok</li>

![Image](https://github.com/user-attachments/assets/ff3f79bd-1257-4b95-b352-6ee81d0c9f80)
<li>scroll down to the pipeline option. in the definition option, select pipeline script from SCM (source code manager). SCM field select Git. for repository url, copy the repo path on github. scroll down to 'Branches to build' and change from */master to */main. in the Script Path field and it should read Jenkinsfile, same as in your repo. select apply + save. now we can run our job. select Build Now</li>

![Image](https://github.com/user-attachments/assets/fb3e11f9-16d7-4d90-ad09-5522ed26903c)



