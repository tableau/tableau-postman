![banner](https://help.tableau.com/current/api/rest_api/en-us/Resources/tableau-logo.png)

tableau-postman

#  Tableau REST API Postman Collection

## Overview
This repo contains an open source collection of Postman requests for each endpoint in the Tableau REST API surface. 

- **[GET STARTED USING THE COLLECTION](#how-to-use-the-collection)**

- **[CONTRIBUTE TO THE COLLECTION IN THE POSTMAN APP](#how-to-contribute)**

- SEE **[COLLECTION ISSUES](https://github.com/tableau/tableau-postman/issues)** 

> **About this repo:** This GitHub repo is used only for [issue tracking](https://github.com/tableau/tableau-postman/issues). Using and contributing to the collection happen in Postman, not in this repo. See the _[How to Use the Collection](#how-to-use-the-collection)_ and _[How to Contribute](#how-to-contribute)_ sections of this README.

> **About the Tableau REST API:** The Tableau REST API enables you to perform many of the actions available through the Tableau UI from scripts or programs. Resources you may find useful: <br/>- Find details for each method the [REST API reference](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api.htm).<br/>- Join the [Tableau Developer Program](https://developer.tableau.com) (_includes a free Tableau sandbox!_).<br/>- Slack with REST API creators and users on **Tableau #Datadev** **#help-rest-api**.<br/>- Or the [Tableau REST API Community Forum](https://community.tableau.com/s/topic/0TO4T000000QFAxWAO/rest-api).

> **About this collection:** The preformatted requests in this collection allow you to discover and make calls for each method in the REST API to your Tableau Cloud site or Tableau Server. You can use it to make small administrative changes, prototype the request for your script, see a real example of the response for your request, and more. 
<br/><br/>The collection has also been extensively customized with scripts and environment variables to make it easier to use, and more informative about errors.

## How to Use the Collection

Managing a Postman collections is very similar to working with a Git repo. To get the collection and customize it for your environment, you will take three steps: 

1. [Fork the collection itself](#fork-the-tableau-rest-api-collection).
2. [Fork the environment variables for the collection](#fork-the-environment-variables-for-the-collection).
3. [Customize a few of the variable values](#customize-your-collection)

### Fork the Tableau REST API collection:

1. Go to the [Tableau collection in the Salesforce Postman workspace ](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2) in a browser.
1. Sign in to or create a free Postman account.  
2. Choose the three dots next to **Tableau REST API** to view more actions
   <img src="assets/images/create_a_fork.png">
3. Choose **Create a fork**
4. Name the fork and the Postman workspace you want it to live in 
   <img src="assets/fork_collection.png">
5.  Keep the **Watch original collection** checkbox selected to be alerted whenever updates are available to the collection
6. Choose **Fork collection** 
   
   At this point you should see the collection in your Postman workspace.

### Fork the environment variables for the collection:

1. Go to the [**Environments**  section of the the Salesforce Postman workspace ](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2) .
1. 2. Choose the three dots next to **Tableau REST API Environment** to view more actions
3. Choose **Create a fork**
4. Name the fork. 
1. Make sure to use the same Postman workspace you used for the collection.  
5.  Keep the **Watch original collection** checkbox selected to be alerted whenever updates are available to the collection
6. Choose **Fork collection** 
   
   Now you should see the environment variables in your Postman workspace.

### Customize your collection

To configure the collection for your Tableau environment: 

1. Go to the **Environment Variable** section of Postman and choose **Tableau REST API Environment**.

   <img src="assets/images/environment_variables.png">

2. For the `server` variable value, enter the domain of your Tableau serivce into the `CURRENT VALUE field. For instance: 

   `myserver.example.com` or 
   
   `10ay.online.tableau.com`

3. Create a [Personal Access Token](https://help.tableau.com/current/online/en-us/security_personal_access_tokens.htm) (PAT) for your Tableau site, and insert the PAT name and PAT secret into the `admin-PAT-name` and `admin-PAT-secret` as the `CURRENT VALUE` for those fields. You can also use user name and password, or JWT authentication - you will see variables and Authentication methods in the collection, for each of these auth types. 

4. Authenticate by running a sign in request and BOOM!, you are ready to use the collection.

### Special things to know

- **Auto Authentication** 

  To authenticate yourself in Tableau manually, choose and use one of the authentication methods that matches the credential type that you have configured in your environment variables. You can configure the collection to skip manual authentication and automatically authenticate when you make a request.

  To turn on auto authentication, choose the **Tableau REST API Collection** in Postman at the top level, and then choose the **Variables** tab, and set the current value of `auto-auth` to `true`.

  <img src="assets/images/auto_auth.png">

  > Note that setting `auto-auth` will try any credentials that are configured in sequence. This can cause unexpected errors. For instance, if you have both PAT and username credentials configured in your environment variables, `auto-auth` will use the username when the PAT expires. 

- **Auto Fill environment variables from response values**

  A very common action is to make a REST request in order to find the ID or name of a resource (workbook, user, datasource...) to use that value in the next REST request. Postman allows you to right-clck on the returned value in a request's response body and assign that value to an environment value. 
  
  This collection supplies a comprehensive list of variables for each Tableau resource type. Those variables are also formatted in the URI paths for each request. This means that using an ID or name from a response in the next request is quick, easy, and much less bug prone than copy pasting these values.
## How to Contribute
This collection is open source and we welcome your contributions! 

### Make pull requests

> The first thing to know is that you make your pull requests in the Postman environment, not in this repo!

The steps are very similar to making a pull request in Git:

1. [Create a fork of the collection](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-7d783742-165f-4d10-8c4c-5719fb60fba2/fork?origin=sidebar) in Postman.

2. Make additions or other changes.

3. Choose **Create a pull request** using the three dots to the right of the collection name.

For detailed info, see [creating a Postman pull request for a fork](https://learning.postman.com/docs/collaborating-in-postman/using-version-control/version-control-overview/).

### Report or explore issues

> Issues are tracked in this GitHub repo.

Use the [Issues](https://github.com/tableau/tableau-postman/issues) page of this repo to create or see existing issues with the collection.
## Who to Thank
The Tableau Postman collection is a gift to the Tableau community from three of Tableau's great Solutions Engineers: [Stephen Price](mailto:), [Jeremy Mayo](mailto:), and [Alex Cortez](mailto:). 



 