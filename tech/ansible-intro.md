# A Gentle Introduction to `ansible`

Src: https://www.youtube.com/watch?v=XJpN8qpxWbA

TLDR: A sys-admin toolbox to administrate sys-admin tasks. Uses "playbooks" to do stuff.

### Features

 - *Agentless* - no need for "agent" installation and management (unlike `chef`, which needs a `chef` client installed on all node("client") machines, which can be very time consuming if you have a hundred of these)
 - Python-based; has a lot of Python functionalities
 - Uses `ssh` for secure connections
 - Push-base architecture:
 
 <img src="./assets/ansible_agentless_architecture.png" width="650">
 
 - A playbook contains plays
 - A play contains tasks
 - A task contains modules
