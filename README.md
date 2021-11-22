# emailer

Make it easy to send emails

## Installation

```shell
pip install gmail-emailer
```

## Manual setup / configuration

To use this library, you need to setup a gmail account to send the emails from. 
You can sign up normally, but then you also need to [allow non-secure apps to connect to the account](https://support.google.com/accounts/answer/6010255?hl=en). 

## Usage

```python3
from emailer.emailer import Emailer

emailer = Emailer(to_emails=['an-email-address@whatever.com'],
                  from_email='your-account@gmail.com',
                  from_email_password='your password')

html_str = '<html><body><p>this is an example</p></body></html>'

emailer.send_html_email(subject='Email subject',
                        sent_from='User Name',
                        message_html=html_str)              
```

You can also attach images by incuding them in the `send_html_email` method: 

```python3
images = [ {'path': 'path/to/file.jpg', 'id': 'any identifier you want'} ]

emailer.send_html_email(..., images=images)
```
