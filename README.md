# Github Default Branch Protect

## Agenda
* We will create a very simple Flask REST API
* We will host the web app on Microsoft Azure

## Flask App
* We will create a very simple flask app.
* It takes json data as input and returns json data as well.

## Usage
- Clone the repo. [https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository]
- Generate personal access token with repo read, write and API access. [https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token]
- Set GH_TOKEN as an environment variable with a value that corresponds to a GitHub Token (ie. `export GH_TOKEN=*******`)
- Set the user value in app.py
- Install the following:
  - [Python 3](https://www.python.org/downloads/)
    - `pip install -r requirements.txt`
  - Install `virtualenv` [https://flask.palletsprojects.com/en/2.0.x/installation/]
  - Install azure-cli [https://docs.microsoft.com/en-us/cli/azure/install-azure-cli]
  - Activate the virtual environment.
  - Install flask `pip install Flask`.
  - Install the Azure App Service extention on VScode.
- Go to Run and Debug, choose Flask in the options.
  ![image](https://user-images.githubusercontent.com/95721835/146450810-bd4745ed-792d-4d0e-89c1-5ff148eae61c.png)
- Next go to Azure icon on the left, select + to create a new web app. Give it an arbitrary name.
  ![image](https://user-images.githubusercontent.com/95721835/146450872-7893e9f2-2820-4427-bc30-0dfbe948737e.png)
- Click on the up arrow symbol to deploy. Select the web app and the folder you want to deploy. It is important the zip size be less than 2.048 gB.
  ![image](https://user-images.githubusercontent.com/95721835/146451025-c86b1ad3-7879-4f6b-bcc9-4a1a13ea71b8.png)
- The Flask app is deployed!
- Grab the azure webapp URL from the UI.
  ![image](https://user-images.githubusercontent.com/95721835/146451659-66510dfd-8541-4086-a4f5-90aefd3f790f.png)
- Create github org webhook. [https://docs.github.com/en/developers/webhooks-and-events/webhooks/creating-webhooks]
  ![image](https://user-images.githubusercontent.com/95721835/146451920-d2f5d13f-dc21-418a-84eb-48713dcf0e45.png)
- Add the azure webapp URL to the webhook payload URL.
- Select the individual events radio button and check repositories.
  ![image](https://user-images.githubusercontent.com/95721835/146452031-20c134c7-d129-4a44-a8b3-15d076eaa039.png)
- Content type should be application/json
- Save the Webhook
- Now create a sample repo under github org.
- Branch protection on master branch and a github issues with @mention will be created automatically.

## Reference:
Video -https://www.youtube.com/watch?v=qqinLLccL2E </br>
Code -  https://github.com/zkoppert/Auto-branch-protect </br>
