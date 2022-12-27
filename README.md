3proxy Ansible Role v 1.0
=========

Install and configure HTTP and SOCKS proxy "3proxy" server 

Requirements
------------

OS:
- Alpine (3.15.0, 3.16.0, 3.17.0)
- Debian
- Ubuntu (20.04.5[focal], )

Role Variables
--------------
<style>
table, th, td, tfoot {
  border: 1px solid black;
  border-collapse: collapse; 
}
thead {
  font-size:24px;
  color:#f3f399;
}
tr.odd1 { background:rgb(60, 60, 60)}
p, br { margin-left: 20px }
em { color:#5e5edb }
</style>

<table>
<thead>
<tr class="header" >
<th>Variable</th>
<th>Description</th>
<th>Comment</th>
</tr>
</thead>
<tr class="odd">
<th>prx_version: <em>0.9.4</em> </th>
<th>3Proxy server version (not use with Alpine OS)</th>
<th>"Tiny" version will use for the Alpine</th>
<tr class="even">
<th>prx_http_port: <em>3128</em></th>
<th>Port of HTTP proxy</th>
<th></th>
<tr class="odd">
<th>prx_socks_port: <em>1080</em></th>
<th>Port of SOCKS proxy</th>
<th></th>
<tr class="even">
<th>prx_ftp_port: <em>21</em></th>
<th>Port of FTP server</th>
<th>Experimental option</th>
<tr class="odd">
<th>prx_pop3_port: <em>110</em></th>
<th>Port of POP3</th>
<th>Experimental option</th>
<tr class="even">
<th>prx_admin_port: <em>80</em></th>
<th>Port of admin WEB server</th>
<th>Experimental option</th>
<tr class="odd">
<th>prx_group_id: <em>2000</em></th>
<th> System group ID</th>
<th></th>
<tr class="even">
<th>prx_user_id: <em>2001</em></th>
<th> System user ID</th>
<th></th>
<tr class="odd">
<th>prx_dns:<p>
- <em>1.1.1.1</em><br>
- <em>8.8.8.8</em</th>
<th>List of DNS servers</th>
<th></th>
<tr class="even">
<th>prx_use_ufw: <em>false</em></th>
<th>If you need to use uncomplicated firewall set to "true"</th>
<th>Don't work with Alpine</th>
<tfoot> <th>prx_user:<p>
- name: <em >user</em><br>
- password: <em >user</em></th>
<th>Users of proxy server (accept all connections if empty or undefined)</th>
<th></th>
</tfoot>
</table>

Dependencies
------------

- The make, python utility needed on the target hosts 
- The sshd setup needed on the target hosts. For Alpine: ```setup-sshd```
- ansible-galaxy collection install community.general

Warning
----------------
<b><i>If you use [```prx_use_ufw: false```] yours ports isn't protected agains hackers.</i><\b>

Example Playbook
----------------

```
- hosts: servers
  roles:
  - role: smg.3proxy
```

License
-------

MIT
