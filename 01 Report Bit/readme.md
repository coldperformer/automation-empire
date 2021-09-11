<a href="../01 Report Bit/"><img width=15% src="https://gitlab.com/coldperformer/multimedia/-/raw/main/automation-empire/01%20Report%20Bit/gifs/00%20logo.gif"></a>

# Overview
**Report Bit** is a tool to send customized notifications using different services such as Gmail, SMS, WhatsApp, Telegram, Slack, and Voice.

# Table of Contents
1. [Requirements](#Section1)<br>
2. [Libraries Setup](#Section2)<br>
3. [Gmail Configuration](#Section3)<br> 
    - 3.1 [OAuth2 Client File Setup](#Section31)<br>
    - 3.2  [Application Authorization](#Section32)<br>
4. [Twilio Configuration](#Section4)<br>
5. [Telegram Configuration](#Section5)<br>
6. [Slack Configuration](#Section6)<br>
7. [Pipeline Architecture](#Section7)<br>

<a name=Section1></a>
# 1. Requirements

- Google Account
- WhatsApp Account
- Telegram Account
- Twilio Account
- Slack Account
- Python

<a name=Section2></a>
# 2. Libraries Setup

- To execute the JNotebook, you must contain the respective libraries present in the notebook.
- If the libraries and their functionalities are missing then you can install them using following commands:

    ```pip install requests```

    ```pip install twilio```

    ```pip install ipython```

    ```pip install google-auth-httplib2```

    ```pip install google-auth-oauthlib```

    ```pip install google-api-python-client```

<a name=Section3></a>
# 3. Gmail Configuration

Gmail is a free email service provided by Google. As of 2019, it had 1.5 billion active users worldwide. A user typically accesses Gmail in a web browser or the official mobile app. Google also supports the use of email clients via the POP and IMAP protocols. If you don't have an account, then click at https://accounts.google.com/signup/v2/webcreateaccount?h to create one.

<a name=Section31></a>
## 3.1 OAuth2 Client File Setup

- Go to https://console.cloud.google.com/ and then create a new project.
    <details>

    **<summary>Click here to see the animation view.</summary>**

    <center><img src="https://gitlab.com/coldperformer/multimedia/-/raw/main/automation-empire/01%20Report%20Bit/gifs/01%20Create%20Project.gif"></center>

    </details>

- Next, go to the ```APIs & Services Dashboard``` in the navigation menu in the panel and enable the services.
- Search for Gmail API and click on ENABLE to enable the API for the newly created project.
    <details>

    **<summary>Click here to see the animation view.</summary>**

    <center><img src="https://gitlab.com/coldperformer/multimedia/-/raw/main/automation-empire/01%20Report%20Bit/gifs/02%20Enable%20APIS.gif"></center>

    </details>

- To use the Gmail API, you may need credentials. Click on ```Create credentials``` to get started.
- At the top of the section, click on ```CREATE CREDENTIALS``` and select ```OAuth client ID``` (verifies app to OAuth servers).
    <details>

    **<summary>Click here to see the animation view.</summary>**

    <center><img src="https://gitlab.com/coldperformer/multimedia/-/raw/main/automation-empire/01%20Report%20Bit/gifs/03%20Credentials.gif"></center>

    </details>

- Next, click on ```PUBLISH APP``` in the ```OAuth consent screen``` and ```CONFIRM``` to push your app in production.
- Now go back to Credentials and click on ```CREATE CREDENTIALS``` and select ```OAuth client ID```.
- This time we will set up the application type, and its type will be ```Desktop App``` along with a name.
    <details>

    **<summary>Click here to see the animation view.</summary>**

    <center><img src="https://gitlab.com/coldperformer/multimedia/-/raw/main/automation-empire/01%20Report%20Bit/gifs/04%20Application%20Settings.gif"></center>

    </details>

- Once you have set up the credentials, download the file from the OAuth 2.0 Client IDs area.
- You may like to rename the file because of its complex long name. For example, you can use client_secret.json.
- Congratulation! you have successfully configured the Gmail API and downloaded the client secret. 
- **Note:** The client_secret file should be kept secret!

<a name=Section32></a>
## 3.2 Application Authorization

- Download the JNotebook.ipynb and Google.py file and save it in a directory on your system.
- Next, copy your client secret file that you downloaded earlier in the same directory.
- Run the jupyter notebook on the local server in your web browser and import the libraries.
- You may like to customize your message for the target audience, otherwise execute the cell.
- Next, specify the target user to whom you want to send an email message along with the email title.
- Execute the cell and, you will be redirected to the web browser to authorize the application.
- After authorizing your application, you will get an output as shown below in the code cell.
- It specifies that you have successfully sent an email to the target user.
    <details>

    **<summary>Click here to see the animation view.</summary>**

    <center><img src="https://gitlab.com/coldperformer/multimedia/-/raw/main/automation-empire/01%20Report%20Bit/gifs/05%20Code%20Execution.gif"></center>

    </details>

- **Note:** The application authorization is a one-time process, and you can send/receive 10,000 emails per day using this API.

    ```
    client_secret.json-gmail-v1-(['https://mail.google.com/'],)
    ['https://mail.google.com/']
    Please visit this URL to authorize this application: https://accounts.google.com/o/oauth2/auth?response_type=code&client_id=31925783565-in9okjkl6b4ejl18ssds0mm5le9a0j3k5.apps.googleusercontent.com&redirect_uri=http%3A%2F%2Flocalhost%3A8080%2F&scope=https%3A%2F%2Fmail.google.com%2F&state=dRPDcTdsf27BOmSyyLhQGTaEPpDsEGW&access_type=offline
    gmail service created successfully
    {'id': '17bb5b4f5f77d1bd', 'threadId': '17bb5b4f5f77d1bd', 'labelIds': ['UNREAD', 'SENT', 'INBOX']}
    ```

<a name=Section4></a>
# 4. Twilio Configuration