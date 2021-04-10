# fam-youtube  
### Goal  

An API to fetch latest videos sorted in reverse chronological order of their publishing date-time from YouTube   
for a given tag/search query in a paginated response.  

### Setup Instructions:  

1. Clone the repository on your machine.  
2. Create a google console project and obtain a youtube data api key (see https://developers.google.com/youtube/v3/getting-started  )  
3. Add the GOOGLE_API_KEYS to .env file in the main folder, see the sample .env for understanding.    
4. Go to https://docs.docker.com/engine/install/ link to install docker.  
5. Open the repo using Vscode.  
6. Open the Vscode terminal.   
7. Build and run the docker containers using this command : docker-compose up -d --build  

### Running instructions:  
After successfully running the docker container, go to the app using these api endpoints:  
1. To fetch all the videos stored in the sqlite database use this link  
http://127.0.0.1:8000/api/v1/get-all-videos/  

2. To search a particular video in the database using a search quer use this format :  
http://127.0.0.1:8000/api/v1/search-videos/?search=Premier%20League  

http://127.0.0.1:8000/api/v1/search-videos/?search=<query>
  
 
You can also filter the results stored in our sqlite database using the filter method provided.    

### Requirements successfully met  
- Server should call the YouTube API continuously in background (async) with some interval (say 10 seconds) for fetching the latest videos for a predefined search query and should store the data of videos (specifically these fields - Video title, description, publishing datetime, thumbnails URLs and any other fields you require) in a database with proper indexes.
- A GET API which returns the stored video data in a paginated response sorted in descending order of published datetime.
- A basic search API to search the stored videos using their title and description.
- Dockerize the project.

 Bonus Points:

- Add support for supplying multiple API keys so that if quota is exhausted on one, it automatically uses the next available key.
- Make a dashboard to view the stored videos with filters and sorting options (optional)
