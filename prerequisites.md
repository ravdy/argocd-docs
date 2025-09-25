# Prerequisites For EKS Cluster setup

To set up ArgoCD on Amazon EKS, follow the steps below:

1. Install **Terraform**
2. Install **kubectl**
3. Install and configure **AWS CLI**
4. Create IAM Role for EKS
5. Configure AWS CLI

---

### Install Terraform on Windows

1. Go to the official Terraform download page:  
https://developer.hashicorp.com/terraform/downloads

2. Download the Windows 64-bit ZIP file.

3. Extract the ZIP – it contains a single file: terraform.exe.

4. Move terraform.exe to a folder (e.g., C:\Terraform\).

5. Add this folder to the PATH:

   - Press Win + R, type sysdm.cpl, and press Enter.

   - Go to Advanced → Environment Variables.

   - Under System variables, find Path → click Edit → New.

   - Add C:\Terraform\ (or your chosen folder).

   - Click OK to save.
6. Open a new Command Prompt or PowerShell window and verify:
   ```sh
   terraform -version
   ```


## 🔹 Install kubectl on Windows
1. Download the latest stable kubectl binary:
   ```powershell
   curl -LO "https://dl.k8s.io/release/v1.32.0/bin/windows/amd64/kubectl.exe"
   ```
1. Move the binary to a directory in your system PATH:
   ```powershell
   move .\kubectl.exe C:\Windows\System32\
   ```
1. Verify installation:
   ```powershell
   kubectl version --client
   ```

1. Follow the official AWS documentation:
   👉 [Install AWS CLI on Windows](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)


# For Linux Environments

##  Install terraform on Linux

1. Download terraform based on the OS

   ```
   https://developer.hashicorp.com/terraform/install
   ```
2. unzip the downloaded terraform package

   ```
   unzip terraform_1.13.3_darwin_arm64
   ```
3. move the Terraform binary to /usr/local/bin/:

   ```
   sudo mv terraform /usr/local/bin/
   ```
4. verify terraform is installed
   ```
   terraform -version
   ```

2. Install kubectl on Linux
   ```bash
   # Download the latest stable kubectl binary
   curl -LO "https://dl.k8s.io/release/$(curl -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

   # Make it executable and move to PATH
   chmod +x kubectl
   sudo mv kubectl /usr/local/bin/

   # Verify installation
   kubectl version --client
   ```
3. Install AWS CLI on Linux
   ```bash
   # Download the installer
   curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

   # Unzip and run the installer
   unzip awscliv2.zip
   sudo ./aws/install

   # Verify
   aws --version
   ```
4. Configure AWS CLI
   ```bash
   aws configure
   ```
   - AWS Access Key ID
   - AWS Secret Access Key
   - Default region name (e.g., us-east-1)
   - Default output format (e.g., json)

5. Create IAM Role or user for AWS
