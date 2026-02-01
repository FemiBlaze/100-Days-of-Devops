## Task Summary

I created a temporary Linux user named mariyam on App Server 3 with an account expiration date set to April 15, 2027. This was done to provide time-limited access for a developer working on the Nautilus project, ensuring the account is automatically disabled after the assignment period ends.


## What I Learned

How to create Linux users with an account expiration date using the useradd command

The importance of using temporary user accounts to improve system security

How to identify the correct application server from infrastructure details

How to connect to internal servers securely through a jump server using SSH


## Commands / Configurations Used

# Connected from Jump Server to App Server 3
ssh banner@stapp03

# Verified Correct Server
hostname

# Verified Current User
whoami

# Created User with Account Expiry Date (required sudo privileges)
sudo useradd -e 2027-04-15 mariyam

# Verified Account Expiry Configuration
sudo chage -l mariyam


## Verification Steps Taken

I confirmed I was on the jump host before connecting to the target server

I checked the hostname to ensure I was working on stapp03 (App Server 3)

I verified the user account and expiration date using chage -l mariyam

I confirmed the account expiration was set to Apr 15, 2027 as required


## Challenges Faced

I initially encountered a permission denied error when attempting to create the user without elevated privileges.
This was resolved by rerunning the command with sudo.

I carefully verified whether I was on the jump server or the target server by using hostname and whoami to avoid making changes on the wrong system.


## Key Takeaway

Always confirm the active server and user context before making system changes

Use account expiration dates for temporary access to enforce the principle of least privilege
