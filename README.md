# swarm-bootstrap-poc

```
alias ansibled='docker run -it --rm -e SSH_PRIVATE_KEY=$SSH_PRIVATE_KEY_B64 -e AWS_ACCESS_KEY=$AWS_ACCESS_KEY -e AWS_SECRET_KEY=$AWS_SECRET_KEY -v $(pwd):/playbook sequenceiq/ansible ansible-playbook'
ansibled -i /playbook/hosts -u ec2-user -vvvv /playbook/bootstrap.yml  
```
