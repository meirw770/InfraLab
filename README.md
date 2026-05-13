# InfraLab
infrastructure lab for testing
Hello everyone this repo is for fun and study
you can fork for your pleasure ;-)


MeirW 13/05/2026
[ Git Repository ] (TF, Ansible, Jenkinsfile)
       |
       | (Webhook / Poll)
       v
+-----------------------+
|  Local Machine        |
|  [ Jenkins Server ]   |  <================ (3. Test:  cURL לIP  -LB)
+-----------------------+
   |              |
   | (1)          | (2)
   | Terraform    | Ansible
   | (Build)      | (Configure)
   v              v
======================================================================
[  Azure / DigitalOcean ]

                      +-------------------+
  (Public IP) =======>|   Load Balancer   | (Port 80)
                      +-------------------+
                                | (Round Robin Routing)
             /------------------+------------------\
             |                  |                  |
             v                  v                  v
      +------------+     +------------+     +------------+
      |   Node 1   |     |   Node 2   |     |   Node 3   |
      | (Ubuntu)   |     | (Ubuntu)   |     | (Ubuntu)   |
<-----| Nginx Web  |-----| Nginx Web  |-----| Nginx Web  |---- (Ansible SSH)
      +------------+     +------------+     +------------+
======================================================================
