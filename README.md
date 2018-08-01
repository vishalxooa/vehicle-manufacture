# Deploy Xooa sample to Xooa backend
Xooa samples are repos already available in Github under Xooa org. Deploying this on Xooa backend gives you access to APIs to interact with the chanicode logic written with these samples. 

1. Go to Xooa backend webservice located at <https://d3u0qtw0cf1xi7.cloudfront.net/#>
2. **Login** to the platform. If you dont have an account, you can click on **Sign Up** to create a new account. Once logged in, you will be taken to the main Xooa dashboard. 
3. From the main dashboard, click on **Deploy New** on top left corner to start the deployment process.
3. The first step is to connect your new Xooa login to your Github account. In the main dashboard you should see the **Connect to Git** option. Click it and in the new browser window that opens up, allow Xooa to access your github account.
4. Enter **App Name** and **Description** for the app. These fields are for you to identify a particular app from list so make sure your values are relevant to the app you are deploying. Click **Next**.
5. Select the type of Github account you hold. Since we are working with Xooa organization's samples, select **public** and search for `xooa/vehicle-manufacture`. A list of repos matching the search criteria are shown below. In our case, vehicle-manufacture wil show up. Click **Select** and click **Next**.
6. The next step is deployment details. Select **master** as the branch and **vehicle-manufacturing** as the chaincode from the dropdowns available. Click **Deploy**.
7. Sit back and relax while Xooa sets up the backend. Once Xooa is finished with the process you will see **Success** for all the process listed on screen.
8. You will be redirected to app dashboard once the deployment is complete.

# Connecting UI with Xooa backend

Prerequisite: You will need to have deployed the vehicle-manufacture-network on the Xooa backend before following the steps below. You can check the steps located at <https://github.com/Xooa/vehicle-manufacture-main>


1. Go to your home folder
```
cd $HOME
```
2. Clone the sample from Xooa's github
```
git clone https://github.com/Xooa/vehicle-manufacture.git
```
3. Navigate to the config file `default.json`
```
cd vehicle-manufacture/config/
```
4. Open the config file `default.json` with your favourite text editor and modify the `webSocketURL` and `httpURL`
```
{
  "restServer": {
      // These will change once we move to a production domain
      "webSocketURL": "wss://sandeepapi.tk/api/sandeepxooa5tsmuwxph",
      "httpURL": "https://sandeepapi.tk/api/sandeepxooa5tsmuwxph"
  }
}
```
5. Add another key-pair called `authToken`. This token is copied from the API token that you get when deploying the vehicle-manufacture-network on Xooa backend. If you are not familiar with this then go to <> and follow the steps. Your `default.json` file should now look as below
```
{
  "restServer": {
      // These will change once we move to a production domain
      "webSocketURL": "wss://sandeepapi.tk/api/sandeepxooa5tsmuwxph",
      "httpURL": "https://sandeepapi.tk/api/sandeepxooa5tsmuwxph",
      "authToken": "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcGlLZXkiOiJRQVNYQ0JNLUM0MTRaNk0tSEdSQ1pNUS1KUFdEVDZSIiwiQXBpU2VjcmV0IjoiQjdYMk9TSEJ0VldpQ1lqIiwiaWF0IjoxNTMxMjIwMTAyfQ.SnIV4MX3eNluVkeXtmKeVgEnv1Lt9Ni04DMtAqvN1ZI"  
  }
}
```
