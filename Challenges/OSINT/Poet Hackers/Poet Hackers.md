# Poet Hackers
![image](https://github.com/user-attachments/assets/90ea8f78-64f0-479e-b64b-ebb9a7534c68)

After downloading the file we dicover that it's a poetry, and it's crystal clear that it contains a puzzle whose answer is the flag...

```
I don’t knock — I slip right through,

A shadow unseen, a force you never knew.

In silence, I strike, with no sound or trace,

Leaving you lost in a digital space.

On October 3rd, I made my claim,

A victim’s data, now mine to tame.

No room for mercy, no chance to fight,

I locked it down, in the dead of night.

I’ve breached the walls of the strong and the weak,

No fortress too high, no system too sleek.

And did you hear of my deadly feat,

When the FBI felt my heat?

I moved through their walls, fast and unseen,

Leaving them shattered, their secrets unclean.

Though they tried to strike back and take the lead,

I was always ahead, fulfilling my need.

From stolen files to ransoms bright,

I take what's yours, and vanish from sight.

A master of fear, a shadow in red,

Once I’ve locked it, your data's dead.

So now, tell me, on October 3rd’s grim date,

Who felt my wrath, who met their fate?

Their files now mine, their secrets in tow,

Who suffered the blow that night, do you know?
```

Well, we'll be starting with analyzing the text to understand what shall we do, I'll be highlighting mos significant lines:

1. ```On October 3rd, I made my claim, A victim’s data, now mine to tame.```, it appears like the poet is talking about an attack he's done on October 3rd, where he stole Info, this could relate to a ransomware or something similar...

2. ```And did you hear of my deadly feat,When the FBI felt my heat?```, here the attacker is referencing to an attack he's done on the FBI, a successful one apparently...

3. ```From stolen files to ransoms bright```, Now we're sure it's a ransomware...

4. ```Who suffered the blow that night, do you know?```, the question is clear, who's the victim of an attack this ransomware group did on the 3rd of October

#
A small search to know what Ransomware group we're talking about, we need a group thatmade a successful attack in the FBI, Which means that this will for sur be a veru significant group...

![image](https://github.com/user-attachments/assets/3970601e-979c-4cf0-ab9d-e35a7148c100)

Our poets are **LockBit**, avery well-known Ransomware group that has made a lot of huge attacks, However, we need to know who was the victim of the attack that happened on 3rd of October, Ransomware group always post their breaches on their own Darkweb websites, so We'll be looking for a ```.onion``` link associated with ```LockBit```

![image](https://github.com/user-attachments/assets/0066b3e3-83e2-4774-a55a-01091e5a1056)
![image](https://github.com/user-attachments/assets/8088f789-e547-490a-927a-10cc88af4a15)

| It wasn't that hard tbh, however, now we gotta access this link, I'll be using Brave's ```Tor``` mode:

And we accessed their website, which actually has a cool anti-DDOS system...

![image](https://github.com/user-attachments/assets/27e1a2cb-4aa9-4bd7-8774-b249f6cdc9f4)

A small Ctrl+F searching for ```OCT```:

![image](https://github.com/user-attachments/assets/d03845cd-b93e-4140-bf90-bf1ac8e78470)

and here it is, Voila!

Flag: BAU{tpgagedcare.com.au}
