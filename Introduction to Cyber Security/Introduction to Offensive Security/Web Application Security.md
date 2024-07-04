![imagem](https://github.com/DanielP33/TryHackMe/assets/145346859/0ffdb30e-d603-4aa3-983d-056d5e8733ed)The idea of a web application is that it is a program running on a remote server.

Consider an online shopping application. The web application will read the data about the products and their details from a database server.
A database is used to store information in an organized way.
Examples include information about products, customers, and invoices.
A database server is responsible for many functions, including reading, searching, and writing to the database.
The online shopping web application might need more than one database to access, for example:

    Products database: This database contains details about the products, such as name, images, specifications, and price.
    Customers database: It contains all details related to customers, such as name, address, email, and phone number.
    Sales database: We expect to see what each customer has purchased and how they paid in this database.

![imagem](https://github.com/DanielP33/THM/assets/145346859/1c0d7a83-8937-4e64-abd2-80651340b2ad)


From the user’s perspective, they will only access an elegant online shop where all the technical infrastructure is hidden.

Many companies offer bug bounty programs. A bug bounty program allows the company to offer a reward for anyone who discovers a security vulnerability (weakness) in the company’s systems. 

There are a few main categories of common attacks against web applications. Consider the following steps and related attacks.

    Log in at the website: The attacker can try to discover the password by trying many words. The attacker would use a long list of passwords with an automated tool to test them against the login page.
    Search for the product: The attacker can attempt to breach the system by adding specific characters and codes to the search term. The attacker’s objective is for the target system to return data it should not or execute a program it should not.
    Provide payment details: The attacker would check if the payment details are sent in cleartext or using weak encryption. Encryption refers to making the data unreadable without knowing the secret key or password.


Identification and Authentication Failure:

    Allowing the attacker to use brute force, i.e., try many passwords, usually using automated tools, to find valid login credentials.
    Allowing the user to choose a weak password. A weak password is usually easy to guess.
    Storing the users’ passwords in plain text. If the attacker manages to read the file containing the passwords, we don’t want them to be able to learn the stored password.


Broken Access Control:


    Failing to apply the principle of the least privilege.
    Being able to view or modify someone else’s account by using its unique identifier.
    Being able to browse pages that require authentication (logging in) as an unauthenticated user.


Injection

An injection attack refers to a vulnerability in the web application where the user can insert malicious code as part of their input. One cause of this vulnerability is the lack of proper validation and sanitization of the user’s input.

Cryptographic Failures:

    Sending sensitive data in clear text, for example, using HTTP instead of HTTPS. HTTP is the protocol used to access the web, while HTTPS is the secure version of HTTP. Others can read everything you send over HTTP, but not HTTPS.
    Relying on a weak cryptographic algorithm. One old cryptographic algorithm is to shift each letter by one. For instance, “TRY HACK ME” becomes “USZ IBDL NF.” This cryptographic algorithm is trivial to break.
    Using default or weak keys for cryptographic functions. It won’t be challenging to break the encryption that used 1234 as the secret key.

![imagem](https://github.com/DanielP33/TryHackMe/assets/145346859/5f9727a8-f847-4fb0-986e-9fbeeeae69a0)

Task3

This task will investigate a vulnerable website that uses Insecure Direct Object References (IDOR) 

IDOR: "Insecure direct object references (IDOR) are a type of access control vulnerability that arises when an application uses user-supplied input to access objects directly. The term IDOR was popularized by its appearance in the OWASP 2007 Top Ten."

For this lab we go into "Your Activity" the link would be "https://inventory-management.thm/activity?user_id=11"
![imagem](https://github.com/DanielP33/TryHackMe/assets/145346859/02351c40-dcef-4c9c-a0ba-e4386be9323d)

we wanna change the user_id until we get something different

![imagem](https://github.com/DanielP33/TryHackMe/assets/145346859/0b8785fd-4056-46b5-9eb6-277edffa7079)


We can now click rever to cause DAMAGE

and the flag is "THM{IDOR_EXPLORED}"
