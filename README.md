![banner](https://help.tableau.com/current/api/rest_api/en-us/Resources/tableau-logo.png)

tableau-postman

#  Tableau REST API Postman Collection

## Overview
This repo contains an open source collection of Postman requests for each endpoint in the Tableau REST API surface. 

- **[How to use the collection](#how-to-use-the-collection)**

- **[How to contribute to the collection](#how-to-contribute)** _(in the Postman app)_

- **[View or add issues](https://github.com/tableau/tableau-postman/issues)** _(in this repo)_

> **About this repo:** This GitHub repo is used only for [issue tracking](https://github.com/tableau/tableau-postman/issues). Using and contributing to the collection happen in Postman, not in this repo. See the _[How to Use the Collection](#how-to-use-the-collection)_ and _[How to Contribute](#how-to-contribute)_ sections of this README.

> **About the Tableau REST API:** The Tableau REST API enables you to perform many of the actions available through the Tableau UI from scripts or programs. Resources you might find useful: <br/>- Find details for each method the [REST API reference](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api.htm).<br/>- Join the [Tableau Developer Program](https://developer.tableau.com) (_includes a free Tableau sandbox!_).<br/>- Slack with REST API creators and users on **Tableau #Datadev** **#help-rest-api**.<br/>- Interact with fellow devs in the [Tableau REST API Community Forum](https://community.tableau.com/s/topic/0TO4T000000QFAxWAO/rest-api).

> **About this collection:** The preformatted requests in this collection allow you to discover and make calls for each method in the REST API to your Tableau Cloud site or Tableau Server. You can use it to make small administrative changes, prototype the request for your script, see a real example of the response for your request, and more. 
<br/><br/>The collection has also been extensively customized with scripts and environment variables to make it easier to use, and more informative about errors.
___
## How to use the collection

Managing a Postman collection is similar to working with a Git repo. To get the collection and customize it for your environment, you will take three steps: 

1. _In Postman:_ [Fork the collection itself](#fork-the-tableau-rest-api-collection).
2. _In Postman:_ [Fork the environment variables for the collection](#fork-the-environment-variables-for-the-collection).
3. _In your fork_: [Customize a few of the variable values](#customize-your-collection)

Once you have completed these steps you are ready to make requests to your Tableau environment!

Check out [Working with the Collection](#work-with-the-collection) for more info and [Who to Thank](#who-to-thank) to find the original authors of this collection.
___
### **Step 1: Fork the Tableau REST API collection**

1. Go to the [Tableau collection in the Salesforce Postman workspace ](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2) in a browser.
1. Sign in to or create a free Postman account.  
2. Choose the three dots next to **Tableau REST API** to view more actions.
   <img src="assets/images/create_a_fork.png">
3. Choose **Create a fork**.
4. Name the fork and the Postman workspace you want it to live in.
   <img src="assets//images/fork_collection.png">
5.  Keep the **Watch original collection** checkbox selected to be alerted whenever updates are available to the collection.
6. Choose **Fork collection**. 
   
   > At this point you should see the collection in your Postman workspace.

### **Step 2: Fork the environment variables for the collection**

1. Go to the [**Environments**  section of the the Salesforce Postman workspace ](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2) .
1. Choose the three dots next to **Tableau REST API Environment** to view more actions.
3. Choose **Create a fork**.
4. Name the fork. 
1. Make sure to use the same Postman workspace you used for the collection.  
5.  Keep the **Watch original collection** checkbox selected to be alerted whenever updates are available to the collection.
6. Choose **Fork environment**.

   > Now you should see the **Tableau REST API Environment** environment variables in your Postman workspace.

7. Choose the three dots next to the forked environment and rename it to differentiate it from the original.

   > This way, if you want to set up multiple environments for different Tableau servers or sites, you can duplicate the original environment variables and customize credentials and other values per environment.
   

### **Step 3: Customize your collection**

To configure the collection for your Tableau environment: 

1. Go to the **Environment Variable** section of Postman and choose duplicate of **Tableau REST API Environment** that you created.

   <img src="assets/images/environment_variables.png">

2. For the `server` variable value, enter the domain of your Tableau service into the `CURRENT VALUE field. For instance: 

   ```
   myserver.example.com
   ```
    or 
   
   ```
   10ay.online.tableau.com
   ```

3. Create a [Personal Access Token](https://help.tableau.com/current/online/en-us/security_personal_access_tokens.htm) (PAT) for your Tableau site, and insert the PAT name and PAT secret into the `admin-PAT-name` and `admin-PAT-secret` as the `CURRENT VALUE` for those fields. You can also use user name and password, or JWT authentication. You will see variables and Authenticate methods in the collection for each of these auth types. 

4. Modify `content-url` with the contentURL of your site. The contentURL in the following examples is "myWorkbooks":

   ```
   http://MyServer/#/views/myWorkbooks/sheet1

   https://10ay.online.tableau.com/authoring/myWorkbooks/sheet1

   https://us-west-2a.online.tableau.com/#/site/myWorkbooks/home
   ```

5. Set `api-version` to match the version of the Tableau Server or the Tableau Cloud site you use.

6. Save your changes.

6. Authenticate by running a sign in request and BOOM!, you are ready to use the collection.

   See [Auto Authentication](#auto-authentication) to skip manual sign in.

To learn more about using the REST API, try the [Get Started Tutorial](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api_get_started_tutorial_intro.htm) in the API reference.


## Work with the collection

- [Update the collection](#update-the-collection)
- [Use Auto Authentication](#use-auto-authentication)
- [Set environment variables from response values](#set-environment-variables-from-response-values)
- [Advanced usage](#advanced-usage)

#### - **Update the collection**

  To update the collection, choose the three dots next to the collection name, and then choose **Pull changes**.

  <img src="assets/images/pull_changes.png">

--------------
#### - **Use Auto Authentication** 

  To authenticate yourself in Tableau manually, choose and use one of the authentication methods that matches the credential type that you have configured in your environment variables. You can configure the collection to skip manual authentication and automatically authenticate when you make a request.

  To turn on auto authentication, choose the **Tableau REST API Collection** in Postman at the top level, and then choose the **Variables** tab, and set the current value of `auto-auth` to `true`.

  <img src="assets/images/auto_auth.png">

  > Note that if authentication fails with one auth type, `auto-auth` will try the next auth type. This can cause unexpected circumstances or errors, for instance, if you have both PAT and username credentials configured in your environment variables, `auto-auth` will use the username when the PAT expires. Or a method may work with PAT credentials but fail if `auto-auth` falls through to JWT credentials that are not scoped for that method.

-----------
#### - **Set environment variables from response values**

Postman allows you to right-click on the returned value in a request's response body and assign that value to an environment value.  This is helpful because a common action is to make a REST request in order to find the ID or name of a resource (workbook, user, datasource., etc.) in order to use that value in the next REST request. 
  
This collection supplies a comprehensive list of variables for each Tableau resource type. Those variables are also formatted in the URI paths for each request. This means that using an ID or name from a response in the next request is quick, easy, and much less bug prone than copy pasting these values.

<img src="assets/images/assign_id_to_variable.png">
_______

#### - **Advanced Usage**

- **Credentials token, site id, and auto sign in** The response to a sign in request includes a value for `site.id` which is  to populate the `site-id` environment variable, and `credentials.token` which is used to populate the collection variable `api-key`. Every request requires the value of `api-key` as the value of its `X-Tableau-Auth` header to validate that the requester has access permissions. The majority of methods use the `site-id` value to specify the Tableau site being called. 

  Note that, for security purposes, the `api-key` value is shortlived, and needs to be refreshed regularly. When `auto-auth` is `true`, a script in the collection runs before each request that performs the sign in flow, ensuring that the `api-key` value is always valid. When `auto-auth` is `false`, you will need to manually sign in to refresh the `credentials.token` value. A manual sign in script will populate `api-key` when you do.

- **Collection testing script**

- **Setting the accept header**

## How to contribute
This collection is open source and we welcome your contributions! 

### Make pull requests

> Make your pull requests for contributions to the collection **in the Postman environment**, not in this repo!

The steps are very similar to making a pull request in Git:

1. [Create a fork of the collection](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-7d783742-165f-4d10-8c4c-5719fb60fba2/fork?origin=sidebar) in Postman.

2. Make additions or other changes.

3. Choose **Create a pull request** using the three dots to the right of the collection name.

For detailed info, see [creating a Postman pull request for a fork](https://learning.postman.com/docs/collaborating-in-postman/using-version-control/version-control-overview/).

### Report or explore issues

> Issues are tracked **in this GitHub repo**.

Use the [Issues](https://github.com/tableau/tableau-postman/issues) page of this repo to create or see existing issues with the collection.
## Who to Thank
The Tableau Postman collection is a gift to the Tableau community from three of Tableau's great Solutions Engineers: [Stephen Price](https://github.com/stephenlprice), [Jeremy Mayo](https://github.com/jeremymayo), and [Alex Cortez](https://github.com/joseacortez91). 



 
