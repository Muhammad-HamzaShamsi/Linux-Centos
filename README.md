# 🐧 Linux (CentOS / RHEL) Command Reference

![CentOS](https://img.shields.io/badge/CentOS-262577?logo=centos&logoColor=white)
![Red Hat](https://img.shields.io/badge/RHEL-EE0000?logo=redhat&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?logo=gnubash&logoColor=white)
![Type](https://img.shields.io/badge/type-cheat%20sheet-informational)

Essential commands for administering **CentOS / RHEL** servers, plus cheat sheets for the `vim` and `nano` editors.

📄 **Cheat sheets:** [Linux CentOS Commands](Linux%20CentOS%20Commands%20Cheat%20Sheet.pdf) · [Vim](Vim%20Cheat%20Sheet.pdf) · [GNU nano](Cheatsheet%20for%20GNU%20nano.pdf)

## Why CentOS / RHEL?

🖥️ Stable and secure for enterprise servers · ⚙️ Highly configurable · 🌐 Open source with a large community

## Files & directories

```bash
ls -lah        cd /path       pwd            mkdir -p a/b
cp -r src dst  mv old new     rm -rf dir     find / -name "*.log"
cat / less / head -n 20 / tail -f file
grep -rn "pattern" /etc
chmod 750 file chown user:group file
tar -czvf backup.tar.gz dir/  tar -xzvf backup.tar.gz
```

## Packages (yum / dnf)

```bash
sudo dnf install -y httpd     # yum on CentOS 7
sudo dnf update -y
dnf search nginx
rpm -qa | grep java
```

## Services (systemd)

```bash
sudo systemctl start|stop|restart|status httpd
sudo systemctl enable --now httpd
journalctl -u httpd -f
```

## Users & permissions

```bash
sudo useradd -m hamza && sudo passwd hamza
sudo usermod -aG wheel hamza   # sudo access
id hamza ; who ; last
```

## Networking & firewall

```bash
ip a ; ip r ; ss -tulpn
nmcli con show
ping / curl -I / dig example.com
sudo firewall-cmd --permanent --add-port=8080/tcp && sudo firewall-cmd --reload
```

## Monitoring

```bash
top / htop ; free -h ; df -h ; du -sh * ; uptime ; vmstat 1
ps aux | grep java ; kill -9 <pid>
```

## SELinux

```bash
getenforce ; sestatus
sudo setenforce 0              # permissive (temporary)
```
