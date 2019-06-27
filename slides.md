# Web security



# Why?

- Protect user data <!-- .element: class="fragment" -->
- Protect website integrity <!-- .element: class="fragment" -->



# \#fails

- Equifax: 146M Americans affected<!-- .element: class="fragment" -->
  - Name, DOB, SSN
  - Prime target for identity theft!
- Ashley Madison: 60GB worth of data stolen<!-- .element: class="fragment" -->
  - Full account details: Names & email addresses
  - Prime target for blackmail, extortion & public shaming




# Plan
- Things to watch out for
- Crypto (not the currency)
- HTTP




# OWASP

Open Web Application Security Project




# OWASP Top 10 list



1. Injection
2. Broken Auth
3. Sensitive data exposure
4. XML external entities
5. Broken access-control
6. Security misconfiguration
7. XSS (Cross-Site Scripting)
8. Insecure deserialization
9. Using components with known vulnerabilities
10. Insufficient logging & monitoring.



# \#1: Injection
- Injecting code into user input<!-- .element: class="fragment" -->
  - Good old SQL injection<!-- .element: class="fragment" -->
    - https://xkcd.com/327/
  - Command injection<!-- .element: class="fragment" -->
- Consequences:<!-- .element: class="fragment" -->
  - Information leak
  - Data modification
  - Total server pwnage



# \#2: Broken Authentication
- Subtle but very important<!-- .element: class="fragment" -->
- Heavily dependent on the app<!-- .element: class="fragment" -->
- Many different vectors:<!-- .element: class="fragment" -->
  - Brute-force attacks
  - Session ID leakage



# \#2: Broken Authentication
- How to prevent:
  - 2FA
  - bcrypt
  - strong password checks
  - DON'T REINVENT THE WHEEL<!-- .element: class="fragment" -->



# \#3: Sensitive data exposure
- Again, subtle but very important<!-- .element: class="fragment" -->
- Mostly through MitM<!-- .element: class="fragment" -->
 - Use HTTPS!<!-- .element: class="fragment" -->
- Also through error messages<!-- .element: class="fragment" -->



# \#4: XML external entities
- Less common if you don't use XML<!-- .element: class="fragment" -->




# \#5: Broken Access-Control
- Heavily dependent on the app<!-- .element: class="fragment" -->
- Happens when users can see / do more than they should<!-- .element: class="fragment" -->
  - Admin vs non-admin, etc.




# \#6: Security misconfiguration
- Very common issue<!-- .element: class="fragment" -->
  - Default password
  - Open cloud storage
  - Misconfigured HTTP headers (CSP, etc)
  - Verbose logs / error messages on the front-end




# \#7: XSS (Cross-Site Scripting)
- Inject Javascript / HTML in the page<!-- .element: class="fragment" -->
  - Used to be way more common
  - Almost a non-issue with React



# \#8: Insecure deserialization
- Example: Rails YAML bug<!-- .element: class="fragment" -->
  - link: https://codeclimate.com/blog/rails-remote-code-execution-vulnerability-explained/



# \#9: Using components with known vulnerabilities
- Again, Rails YAML bug<!-- .element: class="fragment" -->
- Heartbleed<!-- .element: class="fragment" -->



# \#10: Insufficient logging & monitoring.
- How do you know you've been pwned?<!-- .element: class="fragment" -->



# Crypto: _key_ concepts




# RSA
- Rivest, Shamir and Adleman
- 2 keys
  - One reverses the other, and vice versa
  - We typically keep one private, and give out the other<!-- .element: class="fragment" -->
- Encrypt with the public key, decrypt with the private key<!-- .element: class="fragment" -->
- Sign with the private key, verify with the public key<!-- .element: class="fragment" -->




# RSA: Uses
- SSH
- SSL/TLS




# HTTPS:
- Just plain HTTP over TLS
- Certificates are just signed wrappers around public keys



# HTTP: A stateless protocol




# But how do you keep track of users?




# Cookies
- First (and only) notion of "state" in HTTP
- Basically just key-value strings




# Cookies: How they work
- Server sends a "Set-Cookie" header
- The browser sends that value back in the "Cookie" header of each subsequent request to the same domain




# Sessions
- Server-only concept
- Basically just an object in server memory
- The cookie contains the "id"



# OAuth
- Delegate login to a third-party



# JWT
- Keep the session client-side
- Sign it with crypto so it isn't tampered with



# Questions?



# Thank you
