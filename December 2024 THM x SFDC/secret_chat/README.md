## Secret Chat

### Analysis

```
file chat_leak.pcapng 
```

`chat_leak.pcapng: pcapng capture file - version 1.0` --- the file is an network capture file can be opened using wireshark for analysis

#### exporting files

* file >> export objects >> HTTP

##### there are two files a netcat debain downloadable and another file name `flag` which seems to be intersting:

![flag_export](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/secret_chat/chat_leak_export_Flag_v0.png)<br>

* The flag seems to be an executable which is expecting a 4 digit code

```
type flag
chmod +x flag
./flag
```

![flag_export](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/secret_chat/flag_type_exe.png)<br>

##### By looking into the follow (checking the stream sequence)

* Analyze >> Follow >> TCP Stream or HTTP Stream
* Their is some conversion between 	pam and evi exchanging some passcodes like `3423`, `4333`, `7543`, `3519` and `5454`

![chat_leak_chat.png](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/secret_chat/chat_leak_chat.png)<br>

##### By trying these codes with flag exe file

* `3519` looks to be the correct code which given some output

![chat_leak_chat.png](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/secret_chat/chat_leak_correct_code.png)<br>

##### Decoding the output

* After multiple iterations the given string is base64 encoded

#### FLAG

![flag.png](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/secret_chat/chat_leak_flag.png)<br>


##### This questions might be solved by reverse engineering the flag file, plz do let me know here (could be helpfull for others aswell)
