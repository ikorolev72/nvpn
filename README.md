						nvpn


  What is it?
  -----------
Script for connection with openvpn to nordvpn (https://nordvpn.com ) provider 
	and forwarding packets from internal lan.


  The Latest Version
  ------------------
	version 1.1

  Documentation
  -------------

  Installation
  ------------
1. If you will have problem with dns after you stop nvpn may be you need 
add several lines for solving problem with dnsmasq, dns, resolvconf and vpn

echo 'IGNORE_RESOLVCONF=yes' >> /etc/default/dnsmasq
echo 'nameserver 8.8.8.8' >> /etc/resolv.dnsmasq.conf
echo 'nameserver 8.8.4.4' >> /etc/resolv.dnsmasq.conf
echo 'resolv-file=/etc/resolv.dnsmasq.conf' >> /etc/dnsmasq.conf


2. Put script into /usr/bin/ and set chmod 

cp nvpn /usr/bin
chmod +x /usr/bin/nvpn

Now you can start your vpn connection with your credentials.

# nvpn start uk28.nordvpn.com.tcp443.ovpn
 or 
# nvpn start ../../uk28.nordvpn.com.tcp443.ovpn
 or
# nvpn start /home/user/nordvpn/uk28.nordvpn.com.tcp443.ovpn

Check that your connection secured when open the page 
	https://nordvpn.com on clients machines in internal lan

3. To stop openvpn connection
# nvpn stop 

4. To restart openvpn connection
# nvpn restart

5. If you don't like to enter your login/password you can setup authorisation by file.
	You need create file /root/auth.txt with 2 string: login and password 
	and make it readable only for root 
echo 'my_email@aaa.com' >/root/auth.txt 
echo 'MyPASSword' >>/root/auth.txt 
chown root /root/auth.txt 
chmod 400 /root/auth.txt 

  Licensing
  ---------
	GNU

  Contacts
  --------

     o korolev-ia [at] yandex.ru
     o http://www.unixpin.com















	