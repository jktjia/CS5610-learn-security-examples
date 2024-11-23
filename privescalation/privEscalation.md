# Privilege Escalation

The example demonstrates a privilege escalation vulnerability and how to exploit it.

## Steps to reproduce

1. Install all dependencies

    `$ npm install`

2. Start the **insecure.ts** server

    `$ npx ts-node insecure.ts`

3. In the browser, send a GET request

    ```
        http://localhost:3000/send-form
    ```

4. Try different UserIds and see which one gives you authorized access to change the role of that user.

## For you to do

Answer the following:

1. Briefly explain the potential vulnerabilities in **insecure.ts**
insecure.ts doesn't check that the userId in update-role is the actual user's user id.
2. Briefly explain how a malicious attacker can exploit them.
If an attacker that didn't have admin access got an id for a user that did have admin access, they could use that id to do things that require admin access (like alter a user's role)
3. Briefly explain the defensive techniques used in **secure.ts** to prevent the privilege escalation vulnerability?
secure.ts uses an express session with that has a userId and then checks that the id used for update-role matches the session's userId so an attacker can't pretend to be someone else with admin access when sending the request