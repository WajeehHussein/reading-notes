## Reading Day 6
## [Home Page](/README.md)


# Authentication

## Securing Passwords with Bcrypt Hashing Function

Passwords are the first line of defense against cyber criminals. 

Cryptographic hash algorithms MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible.

### PROBLEMS WITH CRYPTOGRAPHIC HASH ALGORITHM
- Brute Force attack: Hashes can't be reversed, so instead of reversing the hash of the password, an attacker can simply keep trying different inputs until he does not find the right now that generates the same hash value, called brute force attack.

- Hash Collision attack: two input strings of a hash function that produce the same hash result.

BCrypt, IT's SLOW AND STRONG : This method of hashing passwords is solid enough for most web applications that stores users' passwords and other sensitive data.
#
## Basic access authentication
HTTP Basic authentication (BA) implementation is the simplest technique for enforcing access controls to web resources because it does not require cookies, session identifiers, or login pages; rather, HTTP Basic authentication uses standard fields in the HTTP header.
#
### Security
The BA mechanism does not provide confidentiality protection for the transmitted credentials. They are merely encoded with Base64 in transit and not encrypted or hashed in any way. Therefore, basic authentication is typically used in conjunction with HTTPS to provide confidentiality.

Because the BA field has to be sent in the header of each HTTP request, the web browser needs to cache credentials for a reasonable period of time to avoid constantly prompting the user for their username and password. Caching policy differs between browsers.

HTTP does not provide a method for a web server to instruct the client to "log out" the user. However, there are a number of methods to clear cached credentials in certain web browsers. 
#
## Server side
When the server wants the user agent to authenticate itself towards the server after receiving an unauthenticated request, it must send a response with a HTTP 401 Unauthorized status line and a WWW-Authenticate header field.

The WWW-Authenticate header field for basic authentication is constructed as following:

WWW-Authenticate: `Basic realm="User Visible Realm"`

The server may choose to include the charset parameter from `RFC 7617:`

WWW-Authenticate: `Basic realm="User Visible Realm"`, `charset="UTF-8"`

This parameter indicates that the server expects the client to use UTF-8 for encoding username and password (see below).

Client side
When the user agent wants to send authentication credentials to the server, it may use the Authorization header field.

The Authorization header field is constructed as follows:

1. The username and password are combined with a single colon (:).
2. This means that the username itself cannot contain a colon.
The resulting string is encoded into an octet sequence. The character set to use for this encoding is by default unspecified, as long as it is compatible with US-ASCII, but the server may suggest use of UTF-8 by sending the charset parameter.

3.The resulting string is encoded using a variant of Base64 (+/ and with padding).

4.The authorization method and a space (e.g. `"Basic"`) is then prepended to the encoded string.

For example, if the browser uses Aladdin as the username and open sesame as the password, then the field's value is the Base64 encoding of `Aladdin:open` sesame, or `QWxhZGRpbjpvcGVuIHNlc2FtZQ==`. Then the Authorization header field will appear as:

Authorization: `Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==`
#
## Password Managers

Password managers are programs, browser plugins or web services that automate management of large number of different credentials. Most password managers have functionality to allow users to easily use them on websites, either by pasting the passwords into the login form, or by simulating the user typing them in.

Web applications should at least not make password managers job more difficult than necessary by observing the following recommendations:

* Use standard HTML forms for username and password input with appropriate type attributes.

* Implement a reasonable maximum password length, such as 64 characters, as discussed in the Password Storage Cheat Sheet.
* Allow any printable characters to be used in passwords.
* Allow users to paste into the username and password fields.
* Allow users to navigate between the username and password field with a single press of the Tab key.
#
Install via NPM 

`npm install bcrypt`