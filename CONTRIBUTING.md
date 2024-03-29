# Contributing to the Postman Collection

This collection is open source and we welcome your contributions! 

Contributions usually come in the form of enhancements to Postman files or documentation via pull requests as well as by reporting bugs as issues. 

![area chart banner](./assets/images/area-chart-banner.png)

> **About the repository:** This GitHub repository is only used for [issue tracking](https://github.com/tableau/tableau-postman/issues). Use [Salesforce Developer's Postman workspace](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-67cb9baa-e0da-4986-957e-88d8734647e2) to get the latest versions of the collection and environment files for your own use.
> The collection and environment files are hosted on Postman and synchronized to this repository for source control.
>For more information, see the _[How to Use the Collection](README.md#how-to-use-the-collection)_ section.

</br>


### Make a **Postman** pull request

> Make your pull requests (PR) for contributions to the collection **in the Postman environment**, not on this repo!

The basic steps are very similar to making a pull request in Git:

1. Start in a Postman workspace that is public. You can't make a Postman PR from a private workspace. 
   
   > Note that you can move your fork of the Tableau collection from a private workspace to a public one to make a PR and then move it back to your private workspace once the request is merged. For more info, see [Using and managing workspaces](https://learning.postman.com/docs/collaborating-in-postman/using-workspaces/managing-workspaces).

2. [Create a fork of the collection](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/collection/12721794-7d783742-165f-4d10-8c4c-5719fb60fba2/fork?origin=sidebar) in Postman. 

3. Make additions or other changes _(see details in the [following section](#use-environment-variables-for-new-or-changed-methods) of this page)_.

4. Choose **Create a pull request** using the three dots to the right of the collection name.

5. Open an issue in this repo describing the enhancement your pull request makes.


For details, see [creating a Postman pull request for a fork](https://learning.postman.com/docs/collaborating-in-postman/using-version-control/version-control-overview/).

</br>

### Use environment variables for new or changed methods

This collection uses Postman environment variables to enable each person to customize for their own environment without editing requests. To add or change a method's request to the collection: 

1. Determine whether the existing environment variable file already has a variable for each resource the user will need to make the request.
2. If you need to add a variable for your collection change, then for each method: 

   1. Also fork the environment file.
   2. Add the variable to the environment file list 

      ![Add the variable to the environment file list](assets/images/add-environment-variable.png)
      
      > Environment variable names in this collection are simple, lower case, hyphen separated descriptions of the resource they are pointed to.

3. Create a new request.
4. Use the appropriate environment variables in the URI and request body of your request. 

   For example, for the Create Connected App Secret request, 
      note that the `:connected-app-id` path parameter uses the value of the `connected-app-id` environment variable.
      
      ![Add tags to data source example](assets/images/path_param_example.png)
 

### Report or explore issues **in Github** 

> Issues are tracked **in this GitHub repo**.

Use the [Issues](https://github.com/tableau/tableau-postman/issues) page of this repo to create or see existing issues with the collection.  
