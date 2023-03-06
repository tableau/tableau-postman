![banner](https://help.tableau.com/current/api/rest_api/en-us/Resources/tableau-logo.png)

# Tableau REST API Postman Collection

## Overview
This repository contains an open source collection of Postman requests for each method in the [Tableau REST API](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api.htm) surface. 

- **[How to use the collection](#how-to-use-the-collection)**
- **[How to contribute to the collection](#contributing-to-the-postman-respository)** _(in the Postman app)_
- **[View or add issues](https://github.com/tableau/tableau-postman/issues)** _(in this repo)_

</br>

> **About the repository:** This GitHub repository is only used for [issue tracking](https://github.com/tableau/tableau-postman/issues). Usage of the collection and environment files as well as contributions or enhancements to said files will take place in Postman, not on this repository. Therefore, the canonical versions of the Postman collection and environment files are hosted on the [Salesforce Developers Postman workspace](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2). These files will be updated on this repository as well.
> 
>  For more information, see the _[How to Use the Collection](README.md#how-to-use-the-collection)_ section.

> **About the Tableau REST API:** The Tableau REST API enables you to perform many of the actions available through the Tableau UI programmatically in scripts, terminals and applications. Resources you might find useful: 
>
>- For detailed descriptions of each method read the [REST API reference](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api.htm).
>- Join the [Tableau Developer Program](https://developer.tableau.com) (_includes a free Tableau sandbox and an invitation to join the #DataDev workspace on Slack!_).
>- Slack with REST API creators and users on **Tableau #Datadev** **#help-rest-api**.
>- Interact with fellow devs in the [Tableau REST API Community Forum](https://community.tableau.com/s/topic/0TO4T000000QFAxWAO/rest-api).

> **About this collection:** The preformatted requests in this collection allow you to discover and make calls for each method in the REST API to your Tableau Cloud site or Tableau Server. You can use it to make small administrative changes, prototype the request for your script, see a real example of the response for your request, and more. 
>
>The collection has also been enhanced with scripts and environment variables to make it easier to use.

![area chart banner](./assets/images/area-chart-banner.png)

## How to use the collection

To get started, follow these three steps:

1. _In Postman:_ [Fork the collection itself](#step-1-fork-the-tableau-rest-api-collection).
2. _In Postman:_ [Fork the environment variables for the collection](#step-2-fork-the-environment-variables-for-the-collection).
3. _In your fork_: [Declare values for variables](#step-3-declare-values-for-variables).

Once you have completed these steps you are ready to send requests to your Tableau environment!

Check out [Advanced Usage](#advanced-usage) for more additional tips and [Who to Thank](#who-to-thank) to find the original authors of this collection.

</br>

### **Step 1: Fork the Tableau REST API collection**

1. Go to the [Tableau collection in the Salesforce Postman workspace ](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2) in a browser.
2. Sign in to or create a free Postman account.  
3. Choose the three dots next to **Tableau REST API** to view more actions.
![create a fork](assets/images/create_a_fork.png)
4. Choose **Create a fork**.
5. Name the fork and the Postman workspace you want it to live in.
   ![fork collection](assets//images/fork_collection.png)
6.  Keep the **Watch original collection** checkbox selected to be alerted whenever updates are available to the collection.
7. Choose **Fork collection**. 
   
   > At this point you should see the collection in your Postman workspace.

</br>

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
   

### **Step 3: Declare values for variables**

To configure the collection for your Tableau environment: 

1. Go to the **Environment Variable** section of Postman and open the **Tableau REST API Environment** file.

    > ***NOTE:*** You can duplicate your fork to declare environment variables for different Tableau sites and servers. That way each set of environment variables can be saved for later use. 

![environment variables](assets/images/environment_variables.png)

1. For the `server` variable value, enter the domain of your Tableau service into the `CURRENT VALUE` field. For instance: 

   ```
   myserver.example.com
   ```
    or 
   
   ```
   10ay.online.tableau.com
   ```

2. Select the authentication method you wish to use and declare the `CURRENT VALUE` for those fields in the environment file. A detailed description of available methods can be found in the [Authentication section of the API Reference](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api_ref_authentication.htm#sign_in). Authentication methods include Username & Password, [Personal Access Token](https://help.tableau.com/current/online/en-us/security_personal_access_tokens.htm) (PAT), and JWT (Connected Apps).

</br>

>***NOTE:*** Credentials are mapped to individual users which enforce access controls and permissions defined in your Tableau environment. This means that certain methods are only available to admin users and API responses will only contain data that the given user has access to. 
>
>To understand how credentials are kept safe within Postman, refer to the documentation on [initial and current variables](https://learning.postman.com/docs/sending-requests/managing-environments/#adding-environment-variables) as well as [variable types](https://learning.postman.com/docs/sending-requests/variables/#variable-types).
>
>With this in mind it is often preferred by developers to use credentials for an admin user with greater access to API methods while also being able to [impersonate other users](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api_ref_authentication.htm#sign_in) when needed.
>
>| CREDENTIAL                  | VARIABLES              |
>| -----------                 | -----------            |
>| Username & Password         | `admin-username`       |
>|                             | `admin-password`       |
>| Personal Access Token (PAT) | `admin-PAT-name`       |
>|                             | `admin-PAT-secret`     |
>| Connected Apps (JWT)        | `JWT`                  |

</br>

1. Modify `content-url`, the permanent name of a Tableau site. The `content-url` in the following examples is "mySite":

   ```
   http://myServer.com/#/site/mySite/

   https://10ay.online.tableau.com/#/site/mySite
   ```

2. Set `api-version` to match the version of the REST API that you wish to use ([see REST API versioning](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api_concepts_versions.htm#rest_api_versioning)).

3. Save your changes.

4. Authenticate by running a sign in request and BOOM!, you are ready to use the collection.

   See [Auto Authentication](#auto-authentication) to skip manual sign in.

To learn more about using the REST API, try the [Get Started Tutorial](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api_get_started_tutorial_intro.htm) in the API reference.

</br>

![blue-banner](./assets/images/blue-banner.png)

## Advanced Usage

- [Update your forks](#update-your-forks)
- [Automatic Authentication](#automatic-authentication)
- [Set environment variables from response values](#set-environment-variables-from-response-values)

</br>

#### **Update your forks**

  To update your collection forks, select the three dots next to the collection name, and then select **Pull changes**.

  ![pull changes in postman](assets/images/pull_changes.png)

</br>

#### **Automatic Authentication** 

  To authenticate yourself in Tableau manually, choose and use one of the authentication methods that matches the credential type that you have configured in your environment variables. As a quality of life feature, you can configure the collection to skip manual authentication and automatically authenticate when you make a request.

  To turn on auto authentication, choose the **Tableau REST API Collection** in Postman at the top level, and then choose the **Variables** tab, and set the current value of `auto-auth` to `true`.

  ![automatic authentication](assets/images/auto_auth.png)

  >***NOTE:*** The `auto-auth` feature will attempt to login with credentials that possess values inside the `CURRENT VALUE` column of the environment file. 
  >
  >It will try to authenticate with all available credentials and fails silently if any errors occur such as an expired Personal Access Token (PAT). In case all credential attempts fail (in other words automatic authentication failed), the console will notify users that none of the credential methods are valid.
  >
  >Since all available credentials are used, automatic authentication is better suited for workflows where a single user or admin user authenticates to the REST API. Users who wish to test a specific authentication method should perform manual authentication while setting `auto-auth` to false.
  >
  >Automatic authentication can also perform impersonation by setting the  `impersonation` variable to true. This will use the declared `user-id` variable to impersonate.

</br>

#### **Set environment variables from response values**

Postman allows you to right-click on the returned value in a request's response body and assign that value to an environment value.  This is helpful because a common action is to make an initial request in order to obtain the ID or name of a resource (workbook, user, datasource, etc.) in order to use that value in a subsequent request to the REST API. 
  
This collection supplies a comprehensive list of variables for each Tableau resource type. Those variables are also formatted in the URI paths for each request. This means that using an ID or name from a response in the next request is quick, easy, and much less bug prone than copy pasting said values.

![set environment variables from response values](assets/images/assign_id_to_variable.png)

</br>

![up and down chart](./assets/images/up-down-area.png)

## Contributing to the Postman Respository

This collection is open source and we welcome your contributions! 

Contributions usually come in the form of enhancements to Postman files or documentation via pull requests as well as by reporting bugs as issues.

For more information, please refer to [CONTRIBUTING.md](CONTRIBUTING.md).

</br>

> **About the repository:** This GitHub repository is only used for [issue tracking](https://github.com/tableau/tableau-postman/issues). Usage of the collection and environment files as well as contributions or enhancements to said files will take place in Postman, not on this repository. Therefore, the canonical versions of the Postman collection and environment files are hosted on the [Salesforce Developers Postman workspace](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2). These files will be updated on this repository as well.
> 
>  For more information, see the _[How to Use the Collection](README.md#how-to-use-the-collection)_ section.

</br>

## Who to Thank
The Tableau Postman collection is a gift to the Tableau community from three of Tableau's great Solutions Engineers: [Stephen Price](https://github.com/stephenlprice), [Jeremy Mayo](https://github.com/jeremymayo), and [Alex Cortez](https://github.com/joseacortez91). 

</br>
<a href="https://github.com/API-Guild/tableau-postman/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=API-Guild/tableau-postman" />
</a>

###### Made with [contrib.rocks](https://contrib.rocks).

![area chart](./assets/images/area-chart.png)