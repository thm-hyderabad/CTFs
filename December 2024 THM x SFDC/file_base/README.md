## File Base

### Analysis

* The `flag-base.txt` seems to be an base64 encoded sting.

#### By docding the content

```
cat flag-base.txt | base64 -d
```

* By observing the output decoded sting, it might be the content of a file. Therefore we can redirect the decoded sting into some file

```
cat flag-base.txt | base64 -d > flag
```

* The output file is an jpeg image

![flag_image_type_open](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/file_base/flag_image_type_open.png)<br>

##### By analyzing the output image

* Under image metadata the Author and Comment tags has a similar string which is in some flag format

```
exiftool flag
```

![flag_exiftool](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/file_base/flag_exiftool.png)<br>

##### By using ROT13, It got into an proper flag format

![flag](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/file_base/flag.png)<br>
