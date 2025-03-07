Component
Path / Resource
Required Permission
Command

System Logs
/var/log/syslog, /var/log/messages
Read (r)
sudo chmod o+r ... / sudo usermod -aG adm ddagent

MarkLogic Logs
/var/opt/MarkLogic/Logs/*.txt
Read (r)
sudo chmod o+r ... / sudo setfacl -m u:ddagent:r ...

MarkLogic API
http://localhost:8002
Authenticated API Access
Create ddagent user in MarkLogic

System Probe
Kernel capabilities (cap_sys_admin,cap_net_admin,cap_net_raw)
Elevated privileges
sudo setcap cap_sys_admin,cap_net_admin,cap_net_raw+ep $(which system-probe)

Network Stats
/proc/net, /sys/class/net
Read (r)
sudo usermod -aG netdev ddagent
