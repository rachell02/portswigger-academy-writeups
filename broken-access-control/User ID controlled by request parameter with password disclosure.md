**Challenge Solved:** I got access to the administrator account and deleted carlos' account lmao

## Steps
1. On the lab Home page click My Account
2. Log in using the supplied credentials and access the user account page.
3. Open Burpsuite and click Intercept On and refresh the browser page
4. Right click on the request and send it to the Repeater
5. Open the Repeater tab on Burp and change the "id" parameter in the URL to administrator.
6. View the response in Burp and search for the 'password value'
   <img width="778" height="529" alt="image" src="https://github.com/user-attachments/assets/34f25921-ee7a-4063-bd3b-36c38b2643ac" />

7. Copy the value and go back to the browser
8. Log out of your account and Log in to the administrator account. Username: administrator Password: (the value you copied)
9.  Once logged in, click on Admin Panel and delete carlos.
    <img width="1264" height="309" alt="image" src="https://github.com/user-attachments/assets/2fa824f1-dbf7-472a-b297-85d91bbc26e9" />


## Why this happened:
The application only relies on the id parameter to show account data, so anyone can view another user’s information by changing it. 
When I got access to the admin account, it showed that the admin's password in the page was prefilled and could easily be read in the response section.

## How to fix:
- Server side authorization: Instead of trusting the id from the request, the server should use that session or token to check which user is making the request. 
  This way, users can only access their own account data, not anyone else’s.
- Do not put password secrets in responses or in HTML! Always store passwords as hashed values.
