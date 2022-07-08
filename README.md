
<p align="center">
<img
src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/OpsHub-Logo.svg/2560px-OpsHub-Logo.svg.png" width="300" align="center"></p>


# Utility to find Unique Project Pairs

This utility retrieves the total number of unique pairs of projects synced between any two systems in OpsHub Integration Manager. 
***

### Input file
It uses the `input.properties` as the input file which contains attributes like `username`, `password`, `System1`, `System2`, and `url` (OIM instance url) whose values is provided by the user. The password value can be left empty if the user wants to give password via console.

<p align="center">
<kbd>
<img
src="./README Assets/input properties.gif" border: "5px solid #555">
</kbd></p>

***
### Running Utility
The utility comes in Runnable JAR file format which can be run in command prompt using the following command.
```console
java -jar <uniqueProjectPairs>.jar
```
After running utility, we can see the `Total Number of unique Project Pairs` between system 1 and system 2 on console.
***
### Output files
The utility generates two output files.
1. `Output.xls` containing the list of `id` and `Project Name` of unique Project Pairs in system 1 and system 2.
2. `Output.log`contains the all `DEBUG` and `INFO` level logs of the utility during execution.



<p align="center">
<kbd>
<img
src="./README Assets/log file.gif" border: "5px solid #555">
</kbd></p>

### Testing

The utility has been tested across several connectors. Here are few examples listed for reference.

***
* #### Jama - Jira 
***
<p align="right"> 
<img
src="https://jama.lv/img/jama-logo-fit.svg?v=e419a8f" height="30">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img
src="https://wac-cdn.atlassian.com/dam/jcr:9e1841b9-2557-4eb2-ab47-d92428580b02/Jira%20Software@2x-blue.png" height="24">
</p> 



<p align="center">
<kbd>
<img
src="./README Assets/Jama-Jira Integrations.png">
</kbd></p>

<p align="center">
<kbd>
<img
src="./README Assets/Jama-Integration-1.png">
</kbd></p>

<p align="center">
<kbd>
<img
src="./README Assets/Jama Integration-2.png">
</kbd></p>

Console Output :  `Total Number of Unique Pairs of Projects : 3`


<p align="center">
<kbd>
<img
src="./README Assets/Jama-Jira Output.png">
</kbd></p>


Here, there are 2 integrations , comprising of 3 different projects pairs. The integration 1 and integration 2 has one same system 2 project but as a project pair they are different. Hence, we get total number of unique pairs as 3.


***
* #### Jira - Azure DevOps
***
<p align="right">
<img
src="https://wac-cdn.atlassian.com/dam/jcr:9e1841b9-2557-4eb2-ab47-d92428580b02/Jira%20Software@2x-blue.png" height="24">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img
src="https://cdn.productplan.com/wp-content/uploads/2017/06/azuredevops-2x.png" height="30">
</p>

<p align="center">
<kbd>
<img
src="./README Assets/Jira-ADO  configurations.png">
</kbd></p>

Here,` Utility Demo -1` integration is cloned without modifying any project pairs. The output will however, only count them as once, as the utility finds unique number of project pairs.

<p align="center">
<kbd>
<img
src="./README Assets/Jira-ADO Output.png">
</kbd></p>

***
* #### Zendesk - Rally
***
<p align="right">
<img
src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Zendesk_logo.svg/2560px-Zendesk_logo.svg.png" height="40">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img
src="https://res.cloudinary.com/crunchbase-production/image/upload/c_lpad,f_auto,q_auto:eco,dpr_1/v1397750470/ea1077672db5d5725467320ecbbbfce9.png" height="40">
</p>

<p align="center">
<kbd>
<img
src="./README Assets/Zendesk-Rally Output.png">
</kbd></p>

Zendesk doesn't have the concept of projects unlike Rally Instead, it has organizations, therefore the meta API can't return the name of projects and only displays Organization ID.


***
* #### ServiceNow - Zendesk
***
<p align="right">
<img
src="https://unifysolutions.net/supportedproduct/servicenow/servicenow-1.svg" height="28">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img
src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Zendesk_logo.svg/2560px-Zendesk_logo.svg.png" height="40">
</p>

<p align="center">
<kbd>
<img 
     
     
src="./README Assets/ServiceNow-Zendesk Output.png">
</kbd></p>

ServiceNow doesn't contain projects or any equivalent section. Therefore the only ID for ServiceNow projects is `OH_NO_PROJECT`.

***
* #### ServiceNow - Digital.ai Agility
***
<p align="right">
<img
src="https://unifysolutions.net/supportedproduct/servicenow/servicenow-1.svg" height="28">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img
src="https://digital.ai//sites/default/files/pictures/DAI%20Logo%20Dark.png" height="28">
</p>

<p align="center">
<kbd>
<img
src="./README Assets/ServiceNow-Digital.ai Output.png">
</kbd></p>

Although, digital.ai has projects section, the meta API doesn't fetch the project names. Hence only Project ID is displayed.

### Few  more Examples
***
* #### Zendesk - Digital.ai Agility
***
<p align="right">
<img
src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Zendesk_logo.svg/2560px-Zendesk_logo.svg.png" height="40">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://digital.ai//sites/default/files/pictures/DAI%20Logo%20Dark.png" height="28">    </p>

<p align="center">
<kbd>
<img
src="./README Assets/Zendesk-Digital.ai Output.png">
</kbd></p>

***
* #### Rally - Digital.ai Agility
***
<p align="right">
<img
src="https://res.cloudinary.com/crunchbase-production/image/upload/c_lpad,f_auto,q_auto:eco,dpr_1/v1397750470/ea1077672db5d5725467320ecbbbfce9.png" height="40">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://digital.ai//sites/default/files/pictures/DAI%20Logo%20Dark.png" height="28">    
</p>

<p align="center">
<kbd>
<img
src="./README Assets/Rally-Digital.ai Output.png">
</kbd></p>

***
* #### GitHub - Rally
***
<p align="right">
<img
src="https://assets-global.website-files.com/5fec9210c1841a6c20c6ce81/5fec9210c1841abd3ec6d286_githubLogo.png" height="31">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img
src="https://res.cloudinary.com/crunchbase-production/image/upload/c_lpad,f_auto,q_auto:eco,dpr_1/v1397750470/ea1077672db5d5725467320ecbbbfce9.png" height="40">
</p>

GitHub has Repositories instead of Projects. However, the meta API is able to fetch Repo Names as Project Names , therefore both Project ID and Name will be displayed.

<p align="center">
<kbd>
<img
src="./README Assets/GitHub-Rally Output.png">
</kbd></p>


