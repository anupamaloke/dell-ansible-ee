## Ansible Execution-Environment for all Dell Ansible Collections
Follow the below steps to build an Ansible Execution-Environment with all Dell Server and Storage ansible collections and associated dependencies such as for e.g. python SDKs and system packages. 
- Install Ansible-Builder. See [here](https://github.com/ansible/ansible-builder) for more details.
  ```
  pip3 install ansible-builder
  ```
- Clone the repo
  ```
  git clone https://github.com/anupamaloke/dell-ansible-ee.git
  cd dell-ansible-ee
  ```
- Build the execution environment
  ```
  ansible-builder build -v3 -t dell-ansible-ee
  podman images list
  ```
- Install Ansible Navigator. See [here](https://github.com/ansible/ansible-navigator) for more details.
  ```
  pip3 install ansible-navigator
  ```
- Run an ansible playbook
  ```
  ansible-navigator run playbook.yml -i hosts --execution-environment-image dell-ansible-ee --pull-policy missing --mode stdout
  ```
