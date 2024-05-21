```
   ▄   ██   █▀▄▀█ █ ▄▄  
     █  █ █  █ █ █ █   █ 
█     █ █▄▄█ █ ▄ █ █▀▀▀  
 █    █ █  █ █   █ █     
  █  █     █    █   █    
   █▐     █    ▀     ▀   
   ▐     ▀               
```

Welcome to **Vampire**, a powerful tool designed to clone private repositories and seamlessly transfer their code to any other repository via CI/CD pipelines. With **Vampire**, you can manage and duplicate your projects effortlessly.

## Features

- **Clone Private Repositories:** Extract code from your private repositories with ease.
- **Seamless CI/CD Integration:** Automate the process of copying code to any repository you have access to.
- **Public Repository Support:** Works with public repositories too, providing a versatile solution for all your needs.

## How It Works

1. **Setup CI/CD Pipeline:** Configure your CI/CD pipeline to integrate with **Vampire**.
2. **Authenticate:** Ensure **Vampire** has the necessary permissions to access the private repositories.
3. **Clone and Transfer:** **Vampire** will handle the cloning of your private repositories and push the code to the desired destination.

## Getting Started

To get started with **Vampire**, follow these steps:

1. **Fork this Repository:** Begin by forking the **Vampire** repository.
2. **Configure Secrets:** Add your authentication secrets to the CI/CD pipeline configuration.
3. **Modify Pipeline:** Adjust the provided CI/CD pipeline script to fit your specific use case.
4. **Run Pipeline:** Execute the pipeline to start the cloning and transferring process.

## Prerequisites
[Settings -> Developer Settings -> Personal access tokens](https://github.com/settings/tokens)
- [x] repo:status - Access commit status
   - [x] repo_deployment - Access deployment status
   - [x] public_repo - Access public repositories
   - [x] repo:invite - Access repository invitations
   - [x] security_events - Read and write security events
- [x] workflow - Update GitHub Action workflows
- [x] write:packages - Upload packages to GitHub Package Registry
   - [x] read:packages - Download packages from GitHub Package Registry
- [x] admin:repo_hook - Write repository hooks
   - [x] write:repo_hook - Write repository hooks
   - [x] read:repo_hook - Read repository hooks
- [x] admin:org_hook - Full control of organization hooks
- [x] gist - Create gists
- [x] project - Full control of projects
   - [x] read:project - Read access of projects

Feel free to customize the content and CI/CD configuration according to your specific needs and preferences.

## Configuring blank

``` 
    - cron: '0 0 * * *' # performs a backup every day at midnight.
```

The cron syntax is structured as follows:

```

 ┌───────────── minute (0-59)
 │ ┌───────────── hour (0-23)
 │ │ ┌───────────── day of the month (1-31)
 │ │ │ ┌───────────── month (1-12)
 │ │ │ │ ┌───────────── day of the week (0-6) (Sunday through Saturday)
 │ │ │ │ │ 
 │ │ │ │ │
 * * * * * 
```

```
repository: 'your_username/your_target_repository'
token: ${{ secrets.VAMP }}
ref: 'main'
```
repository: Replace your_username/your_target_repository with the repository you want to upload to.
Example:
```
repository: 'user/repo1'
```
token: Replace VAMP with the name of the secret key stored in the repository.
ref: Replace main with the branch you want to upload to.

## repositories.txt
The repositories.txt file should contain a list of repositories and branches to be cloned and copied. Each line of the file should contain the repository URL and branch name separated by a space. Here is an example of what repositories.txt might look like:

```
https://github.com/user/repo1.git main
https://github.com/user/repo2.git develop
https://github.com/user/repo3.git feature-branch
```