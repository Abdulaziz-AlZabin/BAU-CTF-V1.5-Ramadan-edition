# Doc
![image](https://github.com/user-attachments/assets/2b30cfcc-b174-481c-b31d-611da8451a24)

When downloading the file, we see that it's a super normal docx file that contains a "Ramadan Mubarak" message, but that's not what I'm looking for...
![image](https://github.com/user-attachments/assets/0c15c386-6f3e-4706-8736-bc8f32ee8f6c)

moving the doc to my kali machine to start playing with...

![image](https://github.com/user-attachments/assets/a66fdf03-3687-42c2-9c4d-66c7db1d4a5c)

```unzipping``` a docx file always is a good first step in sovling this kind of questions, now I'll start exploring the ```xml``` files...

- Found what looks like a B64 text in the ```document.xml```
  ![image](https://github.com/user-attachments/assets/b19b76c2-77ee-43d8-96d0-46613aeca033)

| This means that it's the time to visit my bestfriend, ```CyberChef```

After decoding the text, I found what looks like another kind of encoding:
![image](https://github.com/user-attachments/assets/e63b59d2-414c-4cd6-8732-eb9dd692bd83)

After a small searc, I found out that this is called the DNA cipher, and it relies only on one rule:
```
A: 00
C: 01
G: 10
T: 11 
```

So you know what time it is, it's time to write some code...

This is the decoder I wrote, You can write it in several way, but this is the first one I came up with...
```python
def binary_to_text(binary):
    return ''.join(chr(int(binary[i:i+8], 2)) for i in range(0, len(binary), 8))

def dna_to_binary(dna):
    reverse_mapping = {v: k for k, v in {
        '00': 'A',
        '01': 'C',
        '10': 'G',
        '11': 'T'
    }.items()}
    return ''.join(reverse_mapping[base] for base in dna)

def dna_cipher_decode(dna):
    binary = dna_to_binary(dna)
    text = binary_to_text(binary)
    return text

print(dna_cipher_decode("CAAGCAACCCCCCTGTCGCACGGCCGCACCTTCTGCCGTTCTCCCCTTCGGACGCCCGACCTAGCCTTCGACCGAGCGTTCTCCCTCACCTTCACACATGCAACCTTC"))
```
and when running the code above, we get this output:
![image](https://github.com/user-attachments/assets/489d24d9-a3cb-4e05-bda9-6774db74c495)
