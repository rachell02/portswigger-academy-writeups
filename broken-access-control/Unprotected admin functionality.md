**Challenge Solved:** I accessed the admin panel and deleted Carlos' account 

## Steps
1. On the lab Home page, view the URL 
2. Append robots.txt at the end of the URL
3. See the disallow line discloses the path to the admin panel. (which is /administrator-panel)
   <img width="375" height="110" alt="image" src="https://github.com/user-attachments/assets/22526a69-083e-4c6b-8f55-d6ed89e13cc1" />
4. Replace the /robots.txt at the end of the URL to /administrator panel.
   <img width="846" height="103" alt="image" src="https://github.com/user-attachments/assets/fd3341ed-8efe-40f0-9e30-50f315e23451" />
5. Delete Carlos' account.
   <img width="321" height="199" alt="image" src="https://github.com/user-attachments/assets/c9fc24ff-4677-4ee9-9178-7d34811887db" />


## Why this happened:
The robots.txt is a text file that tells the search engine the pages of the site/app that the owners don't want to appear on the search results. 
In this case, a sensitive path/endpoint was left there.

## How to fix:
- Remove sensitive paths from the robots.txt
- Have proper authentication like checking if the user is an admin.
