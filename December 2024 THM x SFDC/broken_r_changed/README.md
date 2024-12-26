## Broken r Changed

### Analysis

* The downloaded file `broken-1734844014535.png` has an file extension as .png but it is an zip archived file

![ls_type_not_png](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/broken_r_changed/ls_type_not_png.png)<br>

#### unzipping

* There is an `file #1:  bad zipfile offset (local header sig):  0` error
* By looking about this error: it's due to corrupted or invalid file

#### HEX CHECK

* This zip file has improper hex header signature code i.e `89 50 4E 47` which actually belong to png file

```
hexedit broken-1734844014535.png 
```

![improper_hex](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/broken_r_changed/improper_hex.png)<br>

* Editing the proper hex code `50 4B 03 04` for zip file

![proper_hexcode](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/broken_r_changed/proper_hexcode.png)<br>

* After editing the file hex code, The zip is able to be extracted, in which there is a file: `check` 
* This file `check` has a base64 encoded string

```
unzip broken-1734844014535.png 
cat check
```

![zip_ext_check](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/broken_r_changed/zip_ext_check.png)<br>

### FLAG

##### by decoding the hex in extracted file

```
cat check | base64 -d
```

![flag](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/broken_r_changed/flag.png)<br>
