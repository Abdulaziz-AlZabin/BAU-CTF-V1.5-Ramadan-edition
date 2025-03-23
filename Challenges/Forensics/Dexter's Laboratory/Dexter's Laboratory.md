# Dexter's Laboratory
![image](https://github.com/user-attachments/assets/1615746c-dbd9-4048-b3aa-ba072cfcb170)

When downloading the file we see that it's a picture of **Dexter**, So I'll be testing some basic stuff like ```strings```, ```hexedit```, ```binwalk```, ```foremost```, ```exiftool```, ```steghide```...

![image](https://github.com/user-attachments/assets/851d9b29-090d-4d99-865d-93a0a40a58da)

- Now testing ```exiftool``` we find this:```I9VSlRXYFR0XE9VR=UUR```, which appears like a shuffled base64 encoded value...

  ![image](https://github.com/user-attachments/assets/9aa09b0c-cb05-43ba-aaaf-5e5006259108)

Going back to my bestfriend, ```cyberchef``` to look it up, and after applying endiannes swap we got this:

![image](https://github.com/user-attachments/assets/e292633f-95bf-4eaf-8775-db48f4715c87)

But this isn't my flag, so what could this be????

- Testing ```steghide``` :
  ![image](https://github.com/user-attachments/assets/efa3ed95-d173-42bf-ad78-532d98f52c8c)

as we see it asks for a passphrase, which we've just obtained...

![image](https://github.com/user-attachments/assets/6790894b-d734-4fb8-bcc9-382afb603604)
