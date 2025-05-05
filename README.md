# Threat Detection with AWS GuardDuty

This step-by-step guide will help you set up a security demonstration project using AWS GuardDuty to detect credential compromise and unauthorized S3 access<!--more-->

# Project Overview
<ul>
 	<li>Deploy Juice Shop (a vulnerable web app) on AWS EC2</li>
 	<li>Simulate an attack from Kali Linux to steal EC2 credentials</li>
 	<li>Use stolen credentials to access an S3 bucket</li>
 	<li>Monitor all activities with AWS GuardDuty</li>
</ul>
<img class="size-full wp-image-168 aligncenter" src="https://eyemekacyberportfolio.name.ng/wp-content/uploads/2025/05/Untitled-Diagram.drawio.png" alt="" width="185" height="810" />

# Deploy Juice Shop on EC2
Launch EC2 instance (Free Tier eligible t2.micro)
<ul>
 	<li>Launch Instance</li>
 	<li>AMI: Ubuntu Server 22.04 LTS (Free Tier eligible)</li>
 	<li>Instance type: t2.micro</li>
 	<li>Key pair: Create new and download .pem file</li>
 	<li>Network settings: Allow HTTPS/HTTP traffic from anywhere (for the purpose of this project only)</li>
 	<li>SSH into the EC2 and install Juice Shop</li>
 	<li>I deployed Docker and ensured it was running</li>
</ul>
Get public IP from EC2 console and verify Juice Shop is running

<img class="alignnone size-full wp-image-165" src="https://eyemekacyberportfolio.name.ng/wp-content/uploads/2025/05/Screenshot-2025-05-03-134003.png" alt="" width="1563" height="586" />

# Create S3 Bucket with Sensitive File
<ul>
 	<li>Create S3 bucket</li>
 	<li>Upload sample sensitive file</li>
 	<li>Upload to your S3 bucket</li>
</ul>

# Enable GuardDuty
<ul>
 	<li>Enable GuardDuty</li>
</ul>

# Simulate Attack from Kali Linux
<ul>
 	<li>Scan Juice Shop for vulnerabilities</li>
 	<li>nikto -h http://&lt;public-ip&gt;</li>
</ul>

# GuardDuty Detection
<img class="alignnone size-full wp-image-166" src="https://eyemekacyberportfolio.name.ng/wp-content/uploads/2025/05/Screenshot-2025-05-04-180319.png" alt="" width="1134" height="589" />

GuardDuty detected the scan and listed it on the findings and gave a Severity score for it.
