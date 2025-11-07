# Samba-Configuration
sudo yum update
sudo yum upgrade
sudo dnf update -y
sudo yum install samba samba-client samba-common –y

sudo firewall-cmd --permanent --zone=public --add-service=samba
sudo firewall-cmd --reload
sudo systemctl start smb nmb
   sudo systemctl enable  smb nmb
   sudo systemctl status smb nmb
   sudo firewall-cmd --permanent --add-service=samba
   sudo firewall-cmd –reload
sudo chmod -R 755 /file path
   chcon -t samba_share_t /file path
   sudo systemctl restart smb nmb

   vi /etc/samba/smb.conf
{
[File Name]
   path = folder path
   guest ok = yes
   writable = yes
   browsable = yes
   read only = no
   create mask = 0770
   directory mask = 0770
   vfs objects = recycle
           recycle:repository = .recycle_bin
           recycle:touch = yes
           recycle:keeptree = yes
           recycle:versions = yes
           recycle:noversions = *.tmp,*.temp,*.o,*.obj,*.TMP,*.TEMP
           recycle:exclude = *.tmp,*.temp,*.o,*.obj,*.TMP,*.TEMP
           recycle:excludedir = /recycle,/tmp,/temp,/TMP,/TEMP
}
