# Cyberark_apis_v2
Python class of common needed methods of CyberArk APIs (v2)

[Cyberark REST APIs guide](https://docs.cyberark.com/Product-Doc/OnlineHelp/PAS/Latest/en/Content/WebServices/Implementing%20Privileged%20Account%20Security%20Web%20Services%20.htm?tocpath=Developer%7CREST%20APIs%7C_____0)

> **Compatible with:** Python3.6 & above 


<br>

<br>

## Usage
below are common use cases

<br>

```bash
# First, Instantiate an object from the class
cyberark = Cyberark()
```

<br>

* Search for an account

```python
cyberark.search_accounts(search='test-23', safe='test_safe')
# Returns a list of dictionaries
```

<br>

* Get the password of an account

<a id=_get_account_id_></a>

```python
# Fist, we need to get the ID of the account
# > Make sure when you search for the account you get a single item
test_23_id = cyberark.search_accounts(search='test-23', safe='test_safe')[0].get('id')

# Print the password
print(cyberark.get_account_password(test_23_id))
```

<br>

* Update account password

[Get the account ID](#_get_account_id_)

```python
print(cyberark.update_account_password('30_3619', 'POqwer#123m'))
```

<br>

* Delete an account

[Get the account ID](#_get_account_id_)

```python
print(cyberark.delete_account(test_23_id))
```

<br>

* Get all the safes

```python
print(cyberark.get_all_safes())
```

<br>

* Create a new account

```python
print(cyberark.add_account(name='test-23',
                        address='192.168.11.11',
                        userName='test-23',
                        safeName='test-safe',
                        secretType='password',
                        secret='ILoveYouBaby',
                        platformId='pick-one'))
```

