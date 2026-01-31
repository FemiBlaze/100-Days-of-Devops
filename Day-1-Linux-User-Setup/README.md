## Task Summary
I created a Linux user named yousuf with a non-interactive shell on App Server 2 to meet system security and service requirements. The user named yousuf is meant to exist on the system but must not be able to log in interactively.

## What I Learned
- The difference between interactive and non-interactive shells in Linux

- How non-interactive shells like /sbin/nologin improve system security for service accounts

- How to identify the correct server and connect via a jump server using SSH

## Commands / Configurations Used
\`\`\`bash
# Connected from Jump Server to App Server 2
ssh steve@stapp02

# Verified Correct Server
hostname

# Switched to Root User
sudo -i

# Created User with Non-Interactive Shell
useradd yousuf -s /sbin/nologin

# Verified User Creation
grep yousuf /etc/passwd

\`\`\`

## Verification Steps Taken
- I checked the hostname to confirm I was on stapp02

- I verified the user in /etc/passwd

- I confirmed that the shell was set to /sbin/nologin

## Challenges Faced
- I was initially unclear whether I was on the jump server or the target app server. I was able to confirm the active server using hostname. I also was able to confirm active user on entry into the target server using whoami.

## Key Takeaway
- Always confirm which server you are on before making system changes

- Use non-interactive shells for service or automation users to follow the principle of least privilege.
