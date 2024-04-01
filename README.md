# Web_Security_Notes
Web security is an important aspect of an web application. 
**Security** - keeping the data protected from unauthorized sources
**Privacy** - giving the user the information of the which data are collected, how they used, shared, and get consent from the user

## Same-Origin Policy and CORS
same-origin policy in browser privents sites from fetching data's from other sites. if a site needs to get data from other origin it needs to send a request with header mentioning cross-origin access and the server should respond with same header (cross-origin-accept)

## XSS (Cross-site-scripting)
+ **Reflected XSS** happens when user input is directly parsed or send to server without validating it. Should treat the user input as plain text.
+ **Stored XSS** html content is stored in server when send to client without sanitizing attack happens
+ **DOM Based XSS** caused by code run in client side
+ XSS is code injecttion attack where the attacker attach malicious script to a trusted website and send it to a another user

## DOM Based XSS
+ Totally happens inside the client side when the data taken from response is directly inserted into the dom make the browser run if the code contains any js

## XSS in Converting File Content to Text
+ attcker scans the image with js code if the text has js the browser runs it

## XSS in subtitle
+ for video streaming service with uploadable subtitle feature the attacker may upload a subtitle with script tag

## XSS Prevention
+ use an HTML encoder for js before adding an input to dom
+ Don't put untrusted data inside event handlers
+ Encode URI before adding to to url attribute for css
+ Encode before adding links to an a html tag
+ use textContext or innerText for inserting text in dom
+ Untrusted data should only be treated as text
+ Always encode untrusted as which used as string in  js
+ avoid sending untrusted data into html renderer
+ use methods as createElement, setAttribute, appendChild
+ Don't use untrusted data on left side
+ Don't eval json

## Cross Site Request Forgery (CSRF)
Tricks the user into make a malicious request in the autheticated session

## Server Side Request Forgery (SSRF)
Sends a malicious URL to server which reads and may expose a internal service like http enabled database or configurations

## Content Security Policy (CSP)
It is header Allows restriction on a site for loading resources like js, img, script and prevent the site from iframed

## Secure Cookie Attribute
By adding secure attribute the cookies only shared with https protocal with http only it doest shared

## Path Traversal
Aims to access the files in the root directory with setting variable which references an file with '../' value. Thus exposing files in the root directory

## ReDOS
This exploits a service which uses regex, by sending an evil regex which may slow down the service

## Unicode Encoding
Aims to use the decoding mechanism in the applications when decoding unicodes. one example is Path traversal

## Insecure Randomness
Don't use Pseudo-random random number generators such as using a data.now(), the random number should not be predictable

## Error Handling
An application should have a default 404, 500 error pages, if else which lead to the information leak about the backend technology like which frame work used, and it's version

## Double Encoding
Here same data is encoded twice, which may lead to unexpected behaviour of the system or bypass the authorizatinon schemas