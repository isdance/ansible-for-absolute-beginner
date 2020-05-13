Steps to create our lab environment:

**Step 01**: Create a Ubuntu server in Virtual Box. In `Settings->Network`, select `Bridged Adapter`

**Step 02**: Start this box, enable ssh (you will need to install openssh-server). install vim (sudo apt install vim) Then power off this box (sudo shutdown now)

**Step 03**: Clone 3 boxes based on this vm. 1 will be ansible controller, which will have ansible installed. When you clone, make sure to `Generate new mac address`, and choose `Linked clone`

**Step 04**: Change the hostname and hosts file of these boxes

```sh
sudo vim /etc/hostname # change the hostname to ansiblecontroller, ansibletarget1, ansibletarget2
sudo vim /etc/hosts    # change the hosts to localhost ansiblecontroller, localhost ansibletarget1, localhost ansibletarget2

# then restart
sudo shutdown now -r
```

**Step 05**: Install ansible on the `ansiblecontroller`

```sh
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```
