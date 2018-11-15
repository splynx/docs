Signaturit
==========

Signaturit is a Splynx add-on which allows you to complete any signing processes in business with legally binding eSignature.

"Splynx-Signaturit" add-on works in Splynx version 2.0+  

1. To install "Splynx-Signaturit" add-on please enter the command:

```bash
sudo apt update
sudo apt install splynx-signaturit
```
or oyu can install it from Web UI:

*Config -> Integrations -> Add-ons:*

![1.png](1.png)

![2.png](2.png)

![3.png](3.png)


2. To configure add-on "Splynx-Signaturit" you should get "Access token" from [http://app.signaturit.com](http://app.signaturit.com/):

![image2017-8-18_12-17-26.png](image2017-8-18_12-17-26.png)

3. Then check your setup in admin-panel:

_Config -> System -> Signaturit Config_

![image2017-8-18_12-18-9.png](image2017-8-18_12-18-9.png)

4. To be able to send document to the customer you should generate templates from SignaturIt (1) or Splynx (3) or upload them (2) from computer:

![image2017-8-18_12-18-46.png](image2017-8-18_12-18-46.png)

4.1. **To generate document from SignaturIt-template** you have to prepare its template in _SignaturIt-templates_:

![image2017-8-18_12-19-13.png](image2017-8-18_12-19-13.png)

And add at least one field in _Config → SignaturIt Config → Template_:

![image2017-8-18_12-19-40.png](image2017-8-18_12-19-40.png)

Then you can send it:

![image2017-8-18_12-19-57.png](image2017-8-18_12-19-57.png)

Your signature:

![image2017-8-18_12-20-40.png](image2017-8-18_12-20-40.png)

4.2. **To upload the document from PC** click on "_Upload_" icon and in a window poped-up choose the file you'd like to be uploaded:

![image2017-8-18_12-20-58.png](image2017-8-18_12-20-58.png)

Then click on icon "_Send to signature_" and _“Send”_.

Your signature:

![image2017-8-18_12-22-40.png](image2017-8-18_12-22-40.png)

4.3. **To generate document from Splynx-template** you should prepare its template in _Splynx-> Config->Templates_:

![image2017-8-18_12-22-54.png](image2017-8-18_12-22-54.png)

Example of the generated document from Splynx-template:

![image2017-8-18_12-23-15.png](image2017-8-18_12-23-15.png)

Then click on icon "_Send to signature_", write Subject, and click _“Send”_

Signature:

![image2017-8-18_12-23-56.png](image2017-8-18_12-23-56.png)

5. At the end you can download the signed document:

![image2017-8-18_12-24-9.png](image2017-8-18_12-24-9.png)
