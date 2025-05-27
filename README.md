# Asterisk
## Pour une configuration basic 
#### Ubuntu
apt update
apt install asterisk
asterisk -v
cp /etc/asterisk/sip.conf /etc/asterisk/sip.conf.BACKUP
cat <<EOF > /etc/asterisk/sip.conf
[general]
context=esis-sip

allowguest=no
allowoverlap=no
bindport=5060
bindaddr=0.0.0.0
srvlookup=no
disallow=all
allow=ulaw
allow=alaw 
language=fr
alwaysauthreject=yes
canreinvite=yes
nat=yes
session-timers=refuse
localnet=192.168.1.0/255.255.255.0
localnet=192.168.42.0/255.255.255.0
localnet=192.168.43.0/255.255.255.0

; - Video configuration
videosupport=yes
allow=gsm
allow=h263p
allow=h264
allow=vp8

EOF

### Go Asterisk SAMPLES
