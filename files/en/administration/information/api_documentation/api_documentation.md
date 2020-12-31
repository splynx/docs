API Documentation
=============
Splynx system has its own Application Programming Interface (API) which allows software applications to communicate with each other via API calls. In order to simplify the workflow with Splynx API in testing and development you can use [Postman](https://www.postman.com/). *Postman* - is an open source tool and can be easily downloaded [here](https://www.postman.com/downloads/) according to your desired platform. After install the app and sign up for account you can start work on Postman startup screen.

Splynx supports the following type of authentication:

**Access by token**

Generate the token for authorization and GET request. Please note that it's necessary to create an admin user account in Splynx and assign the role e.g. super administrator, it depends on what the access rights you need.

![Postman](postman1.png)
![Postman](postman2.png)

The request method (verb) determines the nature of action you intend to perform.

**Basic authentication**

Add API key with *Unsecure access* in `Administaration → API keys`

Encode you secret phrase to *Base64*, for example on this [web site](https://codebeautify.org/base64-encode)

Copy the encoded text, insert it as a value for *Authorization* key in Postman and press Send. Check the result in *body* section.

![Postman](postman3.png)
![Postman](postman4.png)
![Postman](postman5.png)

The output results indicate that tests were successful.

To get started with Postman, please check its [documentation](https://learning.getpostman.com/).

For more information about Splynx API, please check our wiki page: https://splynx.docs.apiary.io
