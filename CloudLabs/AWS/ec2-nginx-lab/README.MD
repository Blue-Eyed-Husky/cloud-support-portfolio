# nginx lab for ssh troubleshooting
# AWS EC2 + Nginx Hands-On Lab

## Objective
Deploy an EC2 instance, install and run an Nginx web server, and practice troubleshooting access issues using AWS Security Groups.

## Architecture
- AWS EC2 (Ubuntu)
- Nginx web server
- Security Groups (ports 22 and 80)

## Steps Performed
1. Launched an Ubuntu EC2 instance
2. Configured Security Group to allow SSH (22) and http (80)
3. SSH'd into the instance and used amazons instant connect
4. Installed Nginx 
  sudo apt update
  sudo apt install nginx -y
5. Verified web access via public IP
6. Simulated failure by removing SSH access in Security Group
  removed port 22 from Security Group
  test and timed out of ssh access
7. Restored access by correcting Security Group inbounding rules

## Failure Scenario
**Issue:** Unable to SSH into EC2 instance  
**Root Cause:** SSH (port 22) removed from inbound Security Group rules  
**Resolution:** Re-added port 22 from authorized source IP  

## Verification
- `systemctl status nginx` showed service running
- Web server accessible via browser on port 80
- SSH access restored successfully

## Key Learnings
- Security Groups act as a virtual firewall
- Infrastructure issues can block access even when services are running
- Methodical troubleshooting restores service quickly
  
