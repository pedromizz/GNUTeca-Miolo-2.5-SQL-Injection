Presentation:
Security Vulnerability: SQL Injection.
Vulnerability Type: Injections.
Affected Component: Affected function on database acess code.
Software: Gnuteca
Versions: Miolo 2.5
Bussiness area: Colleges and Government

Describle the bug/issue:
SQL Injection in parameter GET of gnuteca application, version miolo 2.5, the attacker may be able to gain unauthorized information

To Reproduce:
Access the Gnuteca application login page (version Miolo 2.5).

Change the request method from POST to GET. This can be done via a browser, a request interceptor (such as Burp Suite), or by modifying the URL directly.

Insert a single apostrophe (') in the login or password field.

Submit the request.

Observe the response: the system returns an SQL syntax error message, indicating that the user input was not properly sanitized.

Impact:
An attacker could exploit this vulnerability to execute arbitrary SQL queries against the database.

Potential consequences include the leak of sensitive data, unauthorized access to user information, and manipulation of system data.

Mitigation Notes:
Use prepared statements/parameterized queries for all user input.

Implement validation and character escaping before sending data to the database.

Review error logs to avoid exposing sensitive details to the end user.
