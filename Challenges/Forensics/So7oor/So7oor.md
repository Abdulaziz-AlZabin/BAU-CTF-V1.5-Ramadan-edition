# So7oor

![image](https://github.com/user-attachments/assets/815312d8-9398-4282-8327-93ca264448ae)

Openning the ```pcapng``` file, we can make a conclusion that this is mainly an ```ICMP``` traffic capture

Exploring the characteristics of the packets we note that for a certain user, the ```Identification``` is much less than usual

These are the normal values :![image](https://github.com/user-attachments/assets/c9f19a2e-ab6f-43b1-8455-8a1b954702ff)![image](https://github.com/user-attachments/assets/deb35dcf-dcaa-4c4e-8a72-91499b41ec24)
![image](https://github.com/user-attachments/assets/6f9bce29-0247-46e8-bc2a-cddf94d44287)

While for the ip ```34.102.136.180```, values were: ![image](https://github.com/user-attachments/assets/38b19fcf-744b-4a11-80ec-e56a22ef4b07)![image](https://github.com/user-attachments/assets/8897a858-9482-4943-9c95-208e8aa0f5fd)![image](https://github.com/user-attachments/assets/f4843a9f-5267-4e75-9ef4-a1fc3c16916f)

So it apears that these values are being modified some how, which raise our suspicion of an exfiltration through this field

I used this to extract the values:
```
sudo tshark -r so7oor.pcapng -Y "icmp && data.len == 1 && ip.dst == 34.102.136.180" -T fields -e ip.id
```

![image](https://github.com/user-attachments/assets/3a109fa5-5fe0-490f-ac85-a9f2b613496a)

Now I want to retrieve the hex value of exactly two digits, I'll be using Bash to extract them and then calculating the decimal values for them...
```
sudo tshark -r so7oor.pcapng -Y "icmp && data.len == 1 && ip.dst == 34.102.136.180" -T fields -e ip.id| awk '{gsub(/^0x0*/, "0x"); printf "%d\n", strtonum($1)}'
```

After that I'll be visiting my bestfriend, ```cyberchef```

![image](https://github.com/user-attachments/assets/8e3bb544-19ff-4e10-9d5f-5d94e3bc6629)

The first thing on the checklist, make an XOR bruteforce...

![image](https://github.com/user-attachments/assets/3461c791-c4ec-4dbd-ba73-7ba308f42813)


