# The Double Shot

![image](https://github.com/user-attachments/assets/f3abc98a-c0ec-4823-b70f-e2ceb15e8c72)
![image](https://github.com/user-attachments/assets/5b4f8066-76b3-4f72-823f-317f52e0b3ab)
![image](https://github.com/user-attachments/assets/5b349006-03ec-47c8-9f4d-5fb04c634f50)

After downloading the ```pcapng``` file, we can see that this is a capture of a traffic mostly made of ```http```, the first question tills us that there was an attck that was done no the server hosting a webservice, and we have to find the attackers, We'll start by tracing ```TCP``` Streams...

![image](https://github.com/user-attachments/assets/d2250dcd-07e2-4e75-af3b-4dc9d0e1ba81)

This leads us that the server was hosting a store that contained an image upload portal, maybe for reviews...

![image](https://github.com/user-attachments/assets/4b7a9fd4-d0c1-4f4e-90b3-0b7dc695e70f)

Also we can see that there's a register portal in the directory ```/bau/```

![image](https://github.com/user-attachments/assets/84aba3e0-53fd-4b54-9b0a-a8a40f0239a2)
 
 We see that a webshell was uploaded here, so we're certain that ```178.77.186.227``` is an attacker

 ![image](https://github.com/user-attachments/assets/0936ba30-5286-4393-8445-15b570f4eb10)

Also here we see the user with ip ```95.141.218.112``` uploaded the well-known malware ```wannacry```

![image](https://github.com/user-attachments/assets/68a48ec9-a098-4a04-bac6-f56dbe069f09)

Here we see that the user with the ip ```178.77.186.227``` used the webshell he's uploaded before and changed the name of ```wannacry.go``` to ```Downloadme```

![image](https://github.com/user-attachments/assets/6dfe844b-0882-455b-9e8f-adfe9795d59e)

Here we see a ```GET``` request on the renamed malware by the user with ip ```189.221.186.227```

Now a small search for the usernames (^_^)

![image](https://github.com/user-attachments/assets/be4ce887-b21f-4db5-b79b-8a53ad9d56d5)![image](https://github.com/user-attachments/assets/dd187ebd-5e78-4f04-b7cf-ef6f84f6519f)

#
Now I have everything to answer my questions...
1. BAU{TheBoyWhoLivedHasComeToDie_178.77.186.227_95.141.218.112}
2. BAU{189.221.186.227}

Now for the third challenge, all I need is a very small search, ```MITRE ID for malware upload```

![image](https://github.com/user-attachments/assets/6b88e1bf-5585-434a-ba44-1585454caff2)

3. BAU{T1608.001}
