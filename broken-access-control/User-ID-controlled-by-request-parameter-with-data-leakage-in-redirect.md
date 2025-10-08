**Challenge Solved:** I obtained the API key for the user carlos  with my given account wiener:peter

## Steps
1. On the lab Home page, click My Account
2. Log in using the given account credentials
3. Open Burpsuite and go to proxy tab
4. Click intercept on, then refresh the page on the browser
5. Send the request to Burp Repeater.
   <img width="609" height="537" alt="image" src="https://github.com/user-attachments/assets/8e428017-f42d-4d89-b0de-7692bd87e156" />

7. Go to Repeater tab and change the "id" parameter to carlos.
8. On the Response section, search for 'api key'.
   <img width="758" height="539" alt="image" src="https://github.com/user-attachments/assets/3519f4f2-aa79-4210-a79f-4dacfa5cad55" />

10. Submit the API key.

## Why this happened:
This happened because the server does not check whether the **request** (with the changed id parameter) actually belongs to the logged-in user.
The application only relies on the **id parameter** to show account data, so anyone can view another user’s information by changing it. 

## How to fix:
When a user logs in, the server gives them a **session or token** to identify who is logged in.
Instead of trusting the id from the request, the server should use that session or token to check which user is making the request. 
This way, users can only access their own account data, not anyone else’s. 
