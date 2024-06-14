# Hands-On with GitLab

Today, I worked with GitLab, performing various tasks including installing, starting, stopping, and uninstalling the GitLab Runner. Additionally, I created repositories with `.gitlab-ci.yml` files, installed a self-hosted GitLab Runner, and used it to run CI/CD pipelines. Below are the steps and commands used during this hands-on session.

## GitLab Runner Installation and Setup

### Ubuntu

1. **Install GitLab Runner**

   ```bash
   curl -L --output /usr/local/bin/gitlab-runner https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64
   sudo chmod +x /usr/local/bin/gitlab-runner
   sudo gitlab-runner install
   sudo gitlab-runner start
   ```

2. **Check GitLab Runner Status**

   ```bash
   sudo gitlab-runner status
   ```

### Amazon Linux

1. **Install GitLab Runner**

   ```bash
   curl -L --output /usr/local/bin/gitlab-runner https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64
   sudo chmod +x /usr/local/bin/gitlab-runner
   sudo gitlab-runner install
   sudo gitlab-runner start
   ```

2. **Check GitLab Runner Status**

   ```bash
   sudo gitlab-runner status
   ```

## Creating Repositories and `.gitlab-ci.yml` Files

1. **Create a New Repository on GitLab**

   - Navigate to your GitLab instance.
   - Click on "New Project" and follow the prompts to create a new repository.

2. **Add a `.gitlab-ci.yml` File**

   - In your new repository, create a `.gitlab-ci.yml` file.
   - Add the desired CI/CD configuration to the file. For example:

     ```yaml
     stages:
       - build
       - test
       - deploy

     build_job:
       stage: build
       script:
         - echo "Building the project..."

     test_job:
       stage: test
       script:
         - echo "Running tests..."

     deploy_job:
       stage: deploy
       script:
         - echo "Deploying the project..."
     ```

## Using a Self-Hosted GitLab Runner

1. **Register the GitLab Runner**

   ```bash
   sudo gitlab-runner register
   ```

   - Follow the prompts to register the runner with your GitLab instance.
   - Choose the executor (e.g., `shell`, `docker`) and provide the necessary details.

2. **Run CI/CD Pipelines**

   - Commit and push the `.gitlab-ci.yml` file to your repository.
   - GitLab will automatically detect the file and trigger the CI/CD pipeline using the self-hosted runner.

## Stopping and Uninstalling GitLab Runner

### Ubuntu

1. **Stop the GitLab Runner Service**

   ```bash
   sudo gitlab-runner stop
   ```

2. **Uninstall GitLab Runner**

   ```bash
   sudo gitlab-runner uninstall
   sudo apt-get remove gitlab-runner -y
   ```

3. **Clean Up Remaining Files**

   ```bash
   sudo rm -rf /etc/gitlab-runner
   sudo rm -rf /var/lib/gitlab-runner
   ```

### Amazon Linux

1. **Stop the GitLab Runner Service**

   ```bash
   sudo gitlab-runner stop
   ```

2. **Uninstall GitLab Runner**

   ```bash
   sudo gitlab-runner uninstall
   sudo yum remove gitlab-runner -y
   ```

3. **Clean Up Remaining Files**

   ```bash
   sudo rm -rf /etc/gitlab-runner
   sudo rm -rf /var/lib/gitlab-runner
   ```

## Conclusion

This hands-on session provided practical experience with GitLab Runner. I learned how to install, start, check status, stop, and uninstall the GitLab Runner on both Ubuntu and Amazon Linux systems. Additionally, I created repositories with `.gitlab-ci.yml` files, registered a self-hosted GitLab Runner, and ran CI/CD pipelines using the runner. These commands and steps serve as a handy reference for future tasks related to GitLab Runner and CI/CD pipelines.
