# The Triple Misery

![image](https://github.com/user-attachments/assets/8e1b251f-7bd3-4a6e-a835-1417a55f98f7)

After downloading the file, we can see that it's a ```.log``` file, which means that we have a small investigation to make, the challenge description says 
```
The triple misery had happened, and the secret is no longer a secret...
```

So this could lead to one of two assumptions:

**The First** is that the logs contain an access to a place where the flag is just laying there

**The Second** is that the flag is hidden somehow through the logs ```You shall be smart and pick this choice since the first isn't logical```

going through the log file, we can see what it's about:

![image](https://github.com/user-attachments/assets/ee0c4e7e-4000-49be-9cd2-3c2cac23fc59)

So our conclusion that these logs are for an ```HTTP``` traffic, which leads us to assume the flag is exfiltrated through the traffic...

I started to investigate the main characteristics of the traffic, and nothing was strange except for two things:

1. All users have normal usernames, all of them but one user: ```AAA```
   
![image](https://github.com/user-attachments/assets/09ffcd55-0f6a-418f-9be4-9ffc9e814126)

2. When reading the logs, we can make a conclusion that the field number 9 is the ```HTTP status codes``` 

![image](https://github.com/user-attachments/assets/b6660cc5-d1fb-4df5-b5a0-1513762d9884)

However, some values aren't from the known HTTP status codes, which means that tese were manipulated

![image](https://github.com/user-attachments/assets/dc2cf507-2b92-4fe4-9b14-14250e59f4c9)

And I wasn't surprised when I saw that these value are only coming from one user exactly, ```AAA```

So we extracted those...

![image](https://github.com/user-attachments/assets/1a294a7e-9ea8-4647-9db3-5f460e34c833)

And I'll be taking those to my **BestFriend**, ```CyberChef```:

![image](https://github.com/user-attachments/assets/79a84c19-56d5-4bad-9350-02eff6c7af44)

so we didn't retrieve the flag yet, but it seems like we're somewhere really close to it, **No Known Encoding** was found, which means we gotta try some stuff, on my own checklist, the first test I usually do is xor brute force:

![image](https://github.com/user-attachments/assets/5c578cf0-9162-4749-b9da-e8d89c6ef85e)
