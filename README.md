# Creating Virtual Machines using GCP and Azure
- Link to VM recording: [Zoom recording via Google Drive](https://drive.google.com/file/d/14dshx_CwPN6I0h6hDJrhaNeZSQHBA8Xl/view?usp=sharing)
- Used Microsoft ClipChamp to trim video

## Timestamps
- 0:00:00 Begins with GCP
- 0:00:39 Walks through VM settings and configurations
- 0:02:25 Creates GCP VM, GCP finishes loading at 0:02:56
- 0:03:17 SSH portion (code screen does not appear during recording but I narrate the commands)
- 0:04:21 Demonstration of stopping instance
- 0:04:40 Demonstrating how to delete instance
- 0:05:04 Naviagting back to VM instances to show the VM is gone

- 0:05:14 Beginning of Azure, loading VM
- 0:05:58 Setting VM configurations/settings
- 0:08:26 Validation passed, created VM
- 0:09:25 deployment of VM complete
- 0:09:47 ran into status issue
- 0:10:40 Connect to VM instructions (download folder, use username/pass created when making VM)
- 0:11:15 Demonstration of stopping VM
- 0:12:02 Demonstration of deleting VM
- 0:12:22 Discussion: similarities, differences, personal preference
- 0:13:49 Double checking to ensure VM was deleted followed by conclusion


## Part 1: Creating a VM in Goolge Cloud Platforms (GCP)
- Navigate to https://cloud.google.com and sign in
- After signing in, navigate to the menu bar on the top left, select "Compute Engine" and "VM Instances"

![GCP menu](images/GCP1.png)

- Select, "Create Instance"
- For this assignment, we will configure our VM utilizing the following setting/options to produce the lowest cost VM possible

![GCP settings](images/GCP2.png)

- Instance name: create a name, omit spaces (ex:assignment1-504)
- Region: us-central1 (Iowa)
- Zone: us-central-1-a
- Series: E2
- Machine type: select e2-micro (reduces cost from $25.46 to $7.11) 
- Navitage to "Operating System and Storage" on the left
- Select "Change"
- Select "Ubuntu" as the operating ssytem 
- Keep the default settings for "Version" and "Boot Disk Type" and hit select
- To keep things simple and ensure we have the lowest cost possible, we will proceed with the default settings under "Data Protection", "Networking", "Observability", "Security", and "Advanced". We will ensure that public IP is ephemeral, network = VPC
- Hit "Create" 
- Now that we have created our VM, click "SSH" and select "Open in browser window"
- Accept the connection and run the following commands:

```bash
   sudo apt-get update
   python3
   exit()
   pwd
   ```
- To stop or delete your instance, navigate back to your VM instances list, select your instance and click "stop" in the three-dot menu bar on the right

![GCP stop and delete menu](images/GCP3.png)

- Once stopped, using the same menu bar, select "Delete" to delete your instance
- To verify that the instance has been deleted, navigate back to the "VM Instances" tab under "Compute Engine". If the VM does not appear then it's been sucessfully deleted


## Part 2: Creating a VM in Microsoft Azure
- Navigate to https://azure.microsoft.com/en-us/
- Once you sign in, navigate to "VM Creation"
- Navigate to "Virtual machines" and click "Create"

![Azure menu](images/Azure1.png)

- To create the lowest cost VM, select the following configurations/settings

![Azure configurations](images/Azure2.png)

- Resource group: Click "Create new", enter name
- VM Name: create a name, no blank spaces
- Region: Select "West US 2"
- Availability options: Keep default
- Security type: Keep default
- Image: Select "Ubuntu Server 24.04 LTS"
- VM architecture: x64
- Size: Click "see all sizes" and select "B1ls"
- Authentication type: select "Password"
- Username: enter a username
- Password: enter a memorable and secure password
- Inbound port rules: keep default settings
- To keep things simple, we will keep the default settings for the remaining sections: "Disks", "Networking", "Management", "Monitoring", "Advanced", "Tags"
- Navigate to "Review and Create", wait for validation to complete and hit "Create"

![Azure VM validation](images/Azure3.png)

- Once created, navitage to "Go to Resource", scroll to "Connect" and download the file. Enter the username and password you created for your VM.
- Return to "Virtual Machines" 
- Select your VM and click "Stop"
- After stopping, click "Delete" to terminate 

![Azure stop and delete](images/Azure5.png)

- Return to "Virtual Machines" to confirm that your VM has been successfully deleted

## GCP vs Azure
### Similarities
- GCP and Azure have a similar flow from naming first, to selecting a region/zone, series etc. 
- Both platforms offer mtuliple Linux distributions
### Differences
- Azure has a faster deployment time compared to GCP
- Azure has many more configuration options
- GCP shows changes in the cost of your VM in real-time with every selection you make while Azure's cost update is not as thorough

### Personal Preference
- I personally prefer GCP due to it's minimalist and simplistic interface. I also like that GCP updates the cost of your VM in real time as you make your configuration selections. 

### Trouble Shooting/Issues
- Before recording, I went through a few practice runs of creating VM's on GCP and Azure. Although I followed the same steps I did for these practice runs, when I got to the Azure section of my recording, an error seemed to occur. After creating my VM, I got a message saying, "assignment1 virtual machine agent status is not ready". Since I wasn't sure what this meant or how to fix it, I did not troubleshot it during the recording as that would've made my video even longer than it already was.
- My video is longer than the set 5-8 minute time limit for this assignment because I ran into an issue during the Azure part of the recording. I tried my best to trim pauses using Microsoft ClipChamp but since I am still new to the software, there were some pauses I was not able to trim. 
- While I walked through the SSH portion of GCP in my recording, the pop up window does not appear on my screen even though it was there. This is likely due to a Zoom setting that blocks pop-up browsers to appear in the live recording. 

## Conclusion
- Both platforms are capable of creating and managing virtual machines effectively. The choice between them will come down to personal preference, existing infrastructure and specific use case requirements. GCP excels in simplicity and pricing transparency, while Azure offers more detailed configuration options and faster deployment speeds. 