# ansible Important cmds 

## installation cmd in ubuntu 
```
    sudo apt update
    sudo apt install software-properties-common
    sudo add-apt-repository --yes --update ppa:ansible/ansible
    sudo apt install ansible
```

## To set linux in UTF-8
```
sudo apt install locales -y
sudo locale-gen en_US.UTF-8
sudo update-locale LANG=en_US.UTF-8

# Apply it for your shell

export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8

# Then reload:

source ~/.bashrc

# Verify

locale
 
```

## cheak for installation and version
```
    ansible --version
    ansible localhost -m ping 
```

## Go inside ansible installed file
``` 
 cd /etc/ansible/
 ls -ltr
 ```

## cheak inital ansible.config and initialize it
```
less ansible.cfg
ansible-config init --disabled -t all > ansible.cfg
```

## Check yml syntax and run playbook
```
ansible-playbook --syntax-check filename.yml  # To check yml
ansible-playbook filename.yml
ansible-playbook filename.yml -K  

#-K will prompt you for your sudo password
# -k(small k) prompts for the SSH/connection password, not the sudo password.
```

### after run 02 playbook nginx is installed and running locally, which we can see by
  ### before and after run playbook run cmd and cheak 
  ```
  nginx 
  sudo nginx -t
 ```
 
  ### to check status of nginx 
  ```
  systemctl status nginx.service
  ```

  ### Incase of failure check port 80 if any server already running or not
   ```
  sudo lsof -i :80
   ```

# For remote server:-

## 1st. add ip in hosts file
## then check it by 
```
ansible-inventory --list
```

## and in playbook set hosts as "localhosts -> all" then run it
```
ansile all -m ping
ansible-playbook filename.yml
```