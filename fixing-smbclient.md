# fixing smbclient

~~
apt-get install libgnutls28-dev
apt-get install libgnutls28-dev
apt-get install libldap2-dev
wget https://download.samba.org/pub/samba/stable/samba-4.5.8.tar.gz
tar xfzv samba-4.5.8.tar.gz
cd samba-4.5.8/
export InstallDir=/opt/samba
./configure --prefix=/opt/samba \
--localstatedir=/opt/samba/var/samba \
--libdir=/opt/samba/lib \
--with-piddir=/opt/samba/var/locks \
--with-logfilebase=/opt/samba/var/log/samba \
--with-privatedir=/opt/samba/etc/private \
--with-configdir=/opt/samba/etc/samba \
--with-lockdir=/opt/samba/var/locks \
--mandir=/opt/samba/man
make
make install
cd /opt/samba/lib/private/
ls | grep "so\.[0-9]$" | while read f; do ln -s $f ${f%.?}; done
ls | grep "so\.[0-9][0-9]$" | while read f; do ln -s $f ${f%.??}; done 
~~~

source: https://forums.offensive-security.com/showthread.php?11957-enum-smb-version&p=59239
