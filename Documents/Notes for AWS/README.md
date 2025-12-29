# Notes for AWS CCP Course

Simplified user to application steps: 
User -> DNS (recursive resolver) -> EC2 (Security Group) -> Application

Correct Flow = user -> DNS -> Internet -> Internet Gateway -> Routing Table -> subnet -> Security Group -> EC2 -> Appliation 
