**Challenge Solved:** I found carlos' password through the live chat view transcript!

## Steps
1. On the Home lab page, Select the Live chat tab.
2. Send any message

   <img width="991" height="813" alt="image" src="https://github.com/user-attachments/assets/bbdb4c22-22ec-4da0-a380-98b6156143af" />

3. Open Burp go to Proxy tab and click Intercept On
4. On the browser, select View transcript.
5. Click Forward on Burp Proxy until you see the GET download transcript (example: GET /download-transcript/5.txt HTTP/2 ), then send it to repeater.

   <img width="599" height="98" alt="image" src="https://github.com/user-attachments/assets/2479b9a9-904b-4266-b2e0-45adea4fcb62" />

6. On Burp Repeater, change the filename to 1.txt then click Send.

    <img width="508" height="116" alt="image" src="https://github.com/user-attachments/assets/d0f09c01-e03b-4cd4-a469-074e2478e1bd" />

7. View the Response section and you'll see the conversation transcript where Carlos tells his password.

<img width="786" height="539" alt="image" src="https://github.com/user-attachments/assets/42c56dc1-cbf4-4041-afc6-3acad0e93865" />

8. Copy the password and return to the main lab page then log in using the stolen credentials.

## Why this happened:
The website happened to have text files of the conversation with predictable names (incrementing numbers) displayed on public URL. 
When the file name was changed, there was no verification of the session/token from the user. 

## How to fix:
- Checking the session/token to confirm if the user owns the transcript.
- Make the files names unguessable
