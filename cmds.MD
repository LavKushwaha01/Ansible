# ansible Important cmds 

## installation cmd in ubuntu 
```
   $ sudo apt update
   $ sudo apt install software-properties-common
   $ sudo add-apt-repository --yes --update ppa:ansible/ansible
   $ sudo apt install ansible
```
## cheak for installation and version
```
    ansible --version'
    ansible localhost -m ping 
```

## Go inside ansible installed file
``` 
 cd /etc/ansible/
 ls -ltr
 ```
