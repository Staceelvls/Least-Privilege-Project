<h1><img src="images/s2pbanner1.JPG"</img></h1>

<h2>Description</h2>
I created this project to demonstrate the idea of Least Privilege in the cloud.
I've always found it easiest to think of Least Privilege like a hotel key card: the user only gets the specific permissions or access they need for their job. For example, a housekeeper gets a key to the rooms they clean, but never the master key or access to the hotel safe.
I built an AWS Identity and Access Management policy to ensure a user could only read a file, but they would be blocked if they tried to delete the file.
<br />


<h2>Languages and Utilities Used</h2>

- <b>JSON</b>
- <b>AWS Management Console</b>

<h2>🖥️Environments Used💻 </h2>

- <b>Amazon Web Services</b>
- <b>AWS Identity and Access Management (IAM)</b>
- <b>S3 Standard Storage</b>

## Project walk-through:



### 1. ☁️ Setup S3 Buckets / Uploaded File
  I created a private S3 bucket and uploaded a file. I will be testing to make sure a user can download this file but not delete it based on the user permissions.
<img src="images/2bucketscreated.JPG" width="800" />
<img src="images/2bucketscreated.JPG" width="800" />
<img src="images/2bucketscreated.JPG" width="800" />
<img src="images/2bucketscreated.JPG" width="800" />
  
---

### 2. 👤 Create the Restricted User 
  I created a new IAM user (RestrictedUser) with a custom password.


<img src="images/iamrole.JPG" width="800" />  

---  
### 3. 📝 Obtain and Configure the Least Privilege Policy
  I used a JSON policy that included only read permissions on the t0p secret bucket, and a few extra permissions to allow the user to see the S3 console page.


<img src="images/lambda.JPG" width="800" />

---
### 4. 🔗 Attach and Test the Policy
  I added the policy to the RestrictedUser and logged in to a separate browser session to test. The user was able to download the file from the bucket, but when the user tried to delete the file, the user received an "Access Denied" error, which was the intended result.


<img src="images/trigger.JPG" width="800" />

---
### 5. File Upload (Input Bucket)
  I uploaded a file named test.txt to the Input Bucket, which automatically starts the Lambda function.


<img src="images/testscreenshot.JPG" width="800" />



---
### 6. MP3 Creation (Output Bucket)
The Python code will read the text and pass it to Amazon Polly.
Then Polly synthesizes the speech, and generates the .mp3 audio stream.
The Lambda function saves the .mp3 file to the Output Bucket, where you can download and listen.


<img src="images/textmp3.JPG" width="800" />


---
### 7. Final Outcome

  <img src="images/mp3player.JPG" width="400" />


[**Click Here to Listen/Download the MP3 Sample**](https://github.com/Staceelvls/Text-2-Speech-Project/raw/refs/heads/main/images/test.mp3)

</p>

<h2>Goal:</h2>
The goal of this project was to create a fully automated, serverless process on AWS that converts text into speech. This project demonstrates my knowledge in connecting cloud services (S3, Lambda, and Polly) to execute an event-driven file conversion pipeline.


---

