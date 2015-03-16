# swarm-bootstrap-poc

This is a small PoC project to create a swarm testing environment on AWS with Ansible.
- starts a few instances
- generates some server keys for Swarm TLS (needs ca certificates) and sets it up on the nodes
- puts together a Swarm node descriptor file
- Starts swarm *managers* on all of the nodes with the file descriptor

To run it use the sequenceiq/ansible docker container:
```
alias ansibled='docker run -it --rm -e SSH_PRIVATE_KEY=$SSH_PRIVATE_KEY_B64 -e AWS_ACCESS_KEY=$AWS_ACCESS_KEY -e AWS_SECRET_KEY=$AWS_SECRET_KEY -v $(pwd):/playbook sequenceiq/ansible ansible-playbook'
ansibled -i /playbook/hosts -u ec2-user -vvvv /playbook/bootstrap.yml  
```
