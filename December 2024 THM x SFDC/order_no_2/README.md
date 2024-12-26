## ordER no: 2

### Analysis
```
>>> "".join(list(map(lambda x: chr(x), ord)))

'ŐĠĴǠŌĘĐČǬǤÀǔżƜÀÜżǐƠÌżǈÄƜƠǐżÀǈƐÌǈǴ'

```

#### By looking into the question:
` "".join(list(map(lambda x: chr(x), ord))) ` (a python code) executed in python shell which provided the output ` 'ŐĠĴǠŌĘĐČǬǤÀǔżƜÀÜżǐƠÌżǈÄƜƠǐżÀǈƐÌǈǴ' `

map: takes two iterable (like a list, tuple, etc.) that contains the items you want to transform. Here it is used along with lamda (a small function).
join: used here to make a string out of list.
ord() takes a single character and returns its Unicode code point (integer).
chr() takes a Unicode code point (integer) and returns the corresponding character.

#### Googing back (rev eng)

```
given_string = 'ŐĠĴǠŌĘĐČǬǤÀǔżƜÀÜżǐƠÌżǈÄƜƠǐżÀǈƐÌǈǴ'
given_string_into_list=list(given_string)
print(given_string_into_list)
```

![string_to_list](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/order_no_2/ord_nn2_v1.png)<br>

##### As per the question the order is 2, in that case if we move to ord 2 using same functions:

```
ord_2= list(map(lambda x: ord(x) >> 2, given_string_into_list))
```

![ord_2](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/order_no_2/ord_no2_v2.png)<br>

##### converting ord --> chr

```
chr2_list = list(map(lambda x: chr(x), ord_2))
```

![chr_2](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/order_no_2/flag-1.png)<br>

#### FLAG

![flag](https://github.com/shybu9/THE_HACKERS_MEETUP/blob/main/writeups/december/order_no_2/ord_2_flag.png)<br>
