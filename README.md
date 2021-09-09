# NewsArticle Website

## Description

Created a web application/site that extracts only relevant articles on the provided query. In addition, also provide the user the choice to save those articles on their respective google drive.

## Tech Stack

1. Python: Primary programming language
2. BeautifulSoup: Python package for parsing HTML and XML documents
3. Django: Web framework that follows the model-template-views architectural pattern
4. External API: Google-Cloud API (for storing data)

## Approach

This is a Website which can be used by an individual who is looking for recent articles on particular topic. Only those articles are shown to the user which are been published by Authors thus signifying the authenticity of the Articles. The user has to provide just one field in the search box: -

    - Keyword/Topic to be searched

## How to setup and run the website
- Clone the repository from github (https://github.com/rishitsahu/BTP)
- Extract all the files from the folder in a fresh folder.
- Open the folder showing all the files of the project.
- Open powershell windows in that folder by following command:
     Shift+Right Click -> Click on open powershell
- Now run the following commands
     1. virtualenv myenv (creating virtual environment)
     2. . myenv/Scripts/activate
     3. pip install -r requirements.txt
     4. python manage.py runserver
 - Website is ready now at port number 8000

## Website Schema
```
 |__website main page
            |___ keyword to be found
                                    |____Article 1
                                    |____Article 2
                                    |____Article 3
                                    |____Article 4
                                    .
                                    .
                                    .
                                    |____Article n
                                                  |____ save button 
                                                                   |_____Google Drive Login
                                                                                           |_____Data Uploaded
                                                                                           |_____Search another
                                                        
            
```

<img src="./f_image1.JPG" style="width: 30%; height:100%;" />


## Design Decisions
 - Used BeautifulSoup for scrapping the articles since we were required to extract artricles from different websites where data is arranged in different    formats.
 - For the backend integration Django is the best framework available right now. Since we were using python as the primary programming language, this python based framework was best suitable for the backend as well as the front end part.
 - Website is designed in such a way that it provides the user a choice to save the articles on their suitable google drives by giving them an option to login with their respective email-id and then saving the article on the drive.

## Generating the API
- Use https://console.cloud.google.com/ for generating API KEY from your service account. Now, enable the cloud API

> **Note:** As of now, credentials of the API will be sent through the mail so I have removed the credentials from the code I am uploading here. Please find it in the mail

## How it works?

1. As and when the last command is run on the powershell a server is created at port no. 8080 

2. Now the user is required to provide the link shown in the powershell in a web browser in this format http://127.0.0.1:8000/.

3. Firstly the keyword is routed to the scrapper as a query and the scrapper scraps the topmost results of the browser for the articles. 

4. Now only those articles are shown to the user which are most relevant. To define the relevancy, we have created various filters in the scrapper, like to filter out the bulky articles, instead just showing a particular paragraph of that article so that the user get an idea of it.

## Results
-Following is the result for searching the keyword "Virat Kohli"

<img src="./result.JPG" style="width: 30%; height:100%;" />

-Providing the save in drive option to the user

<img src="./sav_drive.JPG" style="width: 30%; height:100%;" />

-Providing the user a choice to the drives he/she want to savw in

<img src="./signin.JPG" style="width: 30%; height:100%;" />

<img src="./uploaded.JPG" style="width: 30%; height:100%;" />

## Further Improvements
1. Right now we are crawling for each keyword that has been taken from the user as input. We can improve upon by maintaining a cache database for frequently asked queries from the user.
2. Right now the web application is a good fit for a hundred of users. But as our audience increases the load on the application server would increase and we have to work upon a possible solution. One can be implementing a load balancer for the application server which can route the queries in a balanced manner. Moreover, consistent hashing can be implemented to maintain equal load on multiple servers.
3. We can futher improve the project by deploying a machine learning algorithm which by time learns which are the articles most likely saved by the users, and which are the ones which are disliked by the users and then showing the liked ones at the top and disliked ones at the bottom of the page loaded.

4. We can add more features to facilitate the user like we can add review feature in which user can add their opinions about the article they read and one can decide to read upon those articles based upon rating given by other readers.


## Python packages used

asgiref==3.3.1
beautifulsoup4==4.9.3
cachetools==4.2.0
certifi==2020.12.5
chardet==4.0.0
click==7.1.2
cssselect==1.1.0
Django==3.1.4
feedfinder2==0.0.4
feedparser==6.0.2
filelock==3.0.12
google-api-core==1.24.1
google-api-python-client==1.12.8
google-auth==1.24.0
google-auth-httplib2==0.0.4
google-auth-oauthlib==0.4.2
googleapis-common-protos==1.52.0
httplib2==0.18.1
idna==2.10
jieba3k==0.35.1
joblib==1.0.0
lxml==4.6.2
newspaper3k==0.2.8
nltk==3.5
oauthlib==3.1.0
Pillow==8.1.0
protobuf==3.14.0
pyasn1==0.4.8
pyasn1-modules==0.2.8
python-dateutil==2.8.1
pytz==2020.5
PyYAML==5.3.1
regex==2020.11.13
requests==2.25.1
requests-file==1.5.1
requests-oauthlib==1.3.0
rsa==4.6
sgmllib3k==1.0.0
six==1.15.0
soupsieve==2.1
sqlparse==0.4.1
tinysegmenter==0.3
tldextract==3.1.0
tqdm==4.55.1
uritemplate==3.0.1
urllib3==1.26.2


## Author

Name: Rishit Sahu, Anish Agarwal

Email: 17uec091@lnmiit.ac.in, 17ucs024@lnmiit.ac.in
Phone No.: +91 9588036568, +91 9079374751

https://github.com/rishitsahu
