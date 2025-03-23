# Mojojojojojojojojojojojojo

This is a very basic forensics question, that focuses on your skill in detecting File Signatures and types...
##
![image](https://github.com/user-attachments/assets/c88571d9-c0e3-4266-960f-261aade82289)

After Downloading the file we notice that the file doesn't have a ffile extension, which leads us to assum that we need a ``` File Type Lookup ```

![image](https://github.com/user-attachments/assets/d52bc47e-f009-4305-93b4-587e32c1035f)

Now it's the time for our small investigation, our task is crystal clear, knowing the type of the file, Starting with some basic stuff, We started with ```strings``` and ```file``` 
, Which led to nothing...

![image](https://github.com/user-attachments/assets/3cb29a74-d6be-45f9-b129-42b45ec7be51)

So what we actuall need to start looking up is the signatures of the file, and there's two types of signatures, headers and offsets, now it's crystal clear that the header is missed up since ```file``` couldn't identify the file type, so we'll ne investigating the offset :)

```I'll look it up using hexeditor```

![Screenshot 2025-03-22 160315](https://github.com/user-attachments/assets/2c2c7471-7937-4b78-af2e-511423f5235e)

We found out that the offset value is FF D9, which is a popular signature for JPEG files, if you don't know this info, a small search would be useful (^_^)

![image](https://github.com/user-attachments/assets/9c7f0891-23da-465a-979a-e5f04329c6ab)

I found this on https://www.file-recovery.com/jpg-signature-format.htm

Now that we know what type of file we're dealing with, we'll be trying to fix the header signature, a very well-known source for those signatures is https://en.wikipedia.org/wiki/List_of_file_signatures

![image](https://github.com/user-attachments/assets/4d55f361-fc01-4c9d-a173-4ff754092a68)

and after modifying the header value using hexedit, our image will be rendered successfully...

![image](https://github.com/user-attachments/assets/a13f1d21-8c2d-4897-b05c-2df4ae4944d8)

