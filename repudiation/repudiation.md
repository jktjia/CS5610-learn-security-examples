# Repudiation

The example demonstrates a vulnerability that can lead to repudiation by malicious users attempting to access the services provided by a server.

## Steps to reproduce

1. Install all dependencies

    `$ npm install`

2. Run the server __insecure.ts__.

3. Pretend to be a malicous user and interact with the services by sending requests from the browser.

4. Do you think your actions can be repudiated?

## For you to do

1. Briefly explain the vulnerability.
The insecure version doesn't track what requests are made to the server, so if a malicious user attacks the server, it's impossible to trace what they did and fix it
2. Briefly explain why the vulnerability is addressed in __secure.ts__.
The secure version has a log of all of the requests made to the server that is updated with the time of the request whenever someone sends or retrieves a message or there's some sort of error
3. Which design pattern is used in the secure version to address the vulnerability? Briefly explain how it works?
Each method writes 