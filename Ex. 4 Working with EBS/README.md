# Lab 4 – Working with Amazon Elastic Block Store (EBS)

## Author

* **Name**: Swetha D
* **Register Number**: 212223040222
* **Date of Submission**: 13/3/26

---

## Objective

The objective of this experiment is to understand how Amazon Elastic Block Store (EBS) provides persistent block-level storage for EC2 instances. This lab focuses on creating and attaching an EBS volume, formatting and mounting it on an EC2 instance, storing data, and verifying data persistence after instance reboot.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* An existing EC2 instance (Amazon Linux 2 preferred)
* Basic knowledge of Linux commands

---

## Tools Used

* AWS Management Console
* Amazon EC2
* Amazon EBS
* SSH Client (Terminal / PuTTY)

---

## Tasks Performed

### Task 1: Explore Amazon EBS

Explore the Amazon EBS service through the EC2 dashboard. Observe different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

---

### Task 2: Create an EBS Volume

Create a new EBS volume in the same Availability Zone as the EC2 instance. Choose an appropriate size and volume type.

---

### Task 3: Attach EBS Volume to EC2 Instance

Attach the created EBS volume to the running EC2 instance as an additional block device.

---

### Task 4: Format the EBS Volume

Connect to the EC2 instance using SSH and format the attached volume with a file system (for example, ext4).

---

### Task 5: Mount the EBS Volume

Mount the formatted volume to a directory in the EC2 instance (for example, /data or /mnt/ebs).

---

### Task 6: Store Data in EBS Volume

Create files and directories inside the mounted EBS volume and store sample data.

---

### Task 7: Verify Data Persistence

Reboot the EC2 instance and verify that the data stored in the EBS volume is still available after reboot.

---

## Workflow (Student Explanation)

1. I logged in to the AWS Management Console and opened the Amazon EC2 dashboard. Then, I navigated to the Elastic Block Store (EBS) section and explored the available volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD (io1/io2), Throughput Optimized HDD (st1), and Cold HDD (sc1) to understand their performance and use cases.

2. I created a new EBS volume by selecting the appropriate volume type (gp3), specifying the required storage size, and ensuring that the volume was created in the same Availability Zone as my EC2 instance.

3. After the volume was created, I selected the volume and attached it to my running EC2 instance as an additional block device (for example, /dev/xvdf).

4. I connected to the EC2 instance using SSH and verified the attached volume using the `lsblk` command. Then, I formatted the new volume with the ext4 file system using the command:  
   `sudo mkfs -t ext4 /dev/xvdf`

5. I created a mount directory (for example, /mnt/ebs) and mounted the volume using:  
   `sudo mount /dev/xvdf /mnt/ebs`  
   After mounting, I created sample files and directories inside the mounted location to store test data.

6. To ensure persistence, I rebooted the EC2 instance and verified that the data stored in the EBS volume was still available after the reboot. I also updated the `/etc/fstab` file to automatically mount the volume on system startup.
---

## Output Screenshots (Attach 3)

### Screenshot 1: EBS Volume Created

<img width="1920" height="967" alt="image" src="https://github.com/user-attachments/assets/f9ec2340-3d0c-4fce-8dee-7e615339eb8a" />


---

### Screenshot 2: EBS Volume Attached to EC2

<img width="1920" height="967" alt="image" src="https://github.com/user-attachments/assets/2485628d-f63f-46ac-94e1-d0e2928b9c84" />


---

### Screenshot 3: Mounted Volume with Data

<img width="1920" height="967" alt="image" src="https://github.com/user-attachments/assets/749885a1-2c6d-4238-b174-5709f37b92ab" />


---

## Result / Conclusion

This experiment demonstrated how Amazon EBS provides persistent storage for EC2 instances. By creating, attaching, formatting, and mounting an EBS volume, and by verifying data after reboot, the concept of durable block storage in the cloud was clearly understood.
