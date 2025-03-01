<p align='center'>
  <im src='/images/logo.png' width='200'>
<p>
  
# pw-gen

[![Downloads](https://pepy.tech/badge/pw-gen)](https://pepy.tech/project/pw-gen) ![Version](https://img.shields.io/badge/version-0.1.1-blue) ![Python-Version](https://img.shields.io/badge/python-3.9-blue) ![issues](https://img.shields.io/github/issues/lunAr-creator/pw-gen) ![PyPI - Status](https://img.shields.io/pypi/status/pw-gen) ![License](https://img.shields.io/github/license/lunAr-creator/pw-gen) 


```pw-gen``` is a library whcih deales with generating secure randomised passwords that are customisable and strong simultaneously.
<br></br>
## Installation

Use the package manager [pip](https://pypi.org/project/pip/) to install pw-gen.

```bash
pip install pw-gen
```
#### If you are still using the old version of ```pw-gen``` and want to update it:

```bash
pip install --upgrade pw-gen
```
<br></br>
> **_NOTE:_**  If you are still using older versions of **pw-gen** please download the latest version as examples in this README will likely be incorrect for old versions. Thankyou.

<br></br>
## Basic usage

### Simple passwords (Less Arguments)
```python
from pw_gen import Simple

var = Simple(20)

print(var.generate())
print(var.result())
```

#### Output (Please note that output varies depending on arguments provided)

```
pcWW1QjppIWkzErqjdh8
```
<br></br>
### Complex passwords (More Arguments)

```python
from pw_gen import Complex

var = Complex(20, 'both', include_numbers=True, include_special_chars=True)

print(var.generate())
print(var.result())
```

#### Output (Please note that output varies depending on arguments provided)

```
\{=~#YR>XR@N+Q3K{WFB
```

<br></br>

### Memorable passwords (Easy to remember)

```python
from pw_gen import Memorable

var = Memorable(True)

print(var.generate())
print(var.result())
```

#### Output (Please note that output varies depending on arguments provided)

```
CobrandFlint0825
```

<br></br>
## Creating passwords - An in depth explantation

<details>
<summary>Creating a password</summary>
  
<br>

To customise and generate our password we must first create an instance of our password. This can be acheived by doing **var_name = type_of_password(args)**. This template can be used for all password types. At the moment, there are three varations of a password **Simple, Complex and Memorable**. 
  
 
Simple password require less arguements than a complex password, and it is also a base class that all other variations are derived from. To make a **Simple** password, we can assign to parameters: one of which is mandatory and the other one is optional. The first parameter is password length. This should be an integer. The second one is characters. It defaults to a string of ascii_letters and ascii_digits. However, you can overwrite this by specifying your own as a **string**. Example of how to create a **Simple** password:

```python
from pw_gen import Simple

var1 = Simple(20) # Specifying password length to 20 and characters will default to letters and numbers
var2 = Simple(20, 'abcdefghijklmnopqrstuvwxyz') # Specifying password length to 20 and characters will be set to the ones specified.
```

Complex passwords require 2 mandatory parameters and 2 optional parameters. Param 1 is password length (an int), param 2 is string_method. **string_method** refers to **upper** (upper case), **lower** (lowercase) and **both** (uppercase and lowercase). These arguements should be **strings**. The last two parameters are **include_numbers** (defaults to **True**) and **include_special_chars** (defaults to **False**). These are **keyword-only** parameters. They can be set to **True** or **False**. Therefore, they must be explicitly stated. E.g ```arg=bool``` Example of how to create a **Complex** password:

```python
from pw_gen import Complex

var = Complex(20, 'both', include_numbers=True, include_special_chars=True)
```
Lastly, a Memorable password is a password that can be easily remembered. It uses 2 random words from the ```random_word``` library. It then gets 3-4 random numbers and adds them to the end of the password. We can create a **Memorable** password by assigning 1 parameter which is **include_numbers** (this defaults to **True**). Example of how to create a **Memorable** password:

```python
from pw_gen import Memorable

var = Memorable()
```

</details>

<details>
<summary>Generating a password(s)</summary>
  
<br>

To generate a password we have to use the 'generate' method with our object. The generate method requires no parameters. To generate a password, we will first have to create an object (see **Creating a password**). We then use the ```generate``` method as seen in the example below:

```python
from pw_gen import {insert password type}

var = {insert password type}(args)
var.generate()

# or

print(var.generate)
```

To generate **muliple** passwords we can use a for loop:

```python
from pw_gen import {insert password type}

var = {insert password type}(args)
for i in range(INSERT NUM):
  print(var.generate())
```
<br></br>
> _**Note**_: If you generate one password (_password1_), and then generate another password (_password2_) with the same object, **_password1_** will be cleared and replaced by **_password2_**. Therefore,  if you would like to **keep** a password, simply append it to a list of passwords or or store them in a file, database etc.

</details>

<details>
<summary>Returning a password</summary>

<br>

To return a generated password we can simple use the ```result()``` method:

```python
from pw_gen import {insert password type}

var = {insert password type}(args)
print(var.generate())
print(var.result())
```

</details>

<br></br>

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
https://opensource.org/licenses/MIT

## PYPI page:
https://pypi.org/project/pw-gen/
