**Jira Re-indexing**

Re-indexing is often needed after major configuration change in Jira

Once certains fields have been created or modified in Jira, this could result in making the search index becoming out-of-sync Jira Instance configuration.

Example of configuration details that might require these changes and return incorrect queries are as follows;

- Field configuration schemes
- Custom fields
- Plugins 
- Time tracking



When this happens, a similar message as shown below will be displayed in your Administrative view.

    ***Someone** made configuration changes to 'SECTION' at TIME. It is recommended that you perform a re-index. It is recommended that you perform a re-index. For more information, please click the Help icon.
    To perform the re-index now, please go to the 'Indexing' section.
    Note: So that you only have to re-index once, you may wish to  complete any other configuration changes before performing the re-index.  

To resolve this errors, simple re-index your jira instance.

**Note:** A background re-indexing is advisable as this does not affect the system as users can continue working.
After, indexing, remember to acknowledge. 


**Links:** [https://confluence.atlassian.com/adminjiraserver071/re-indexing-after-major-configuration-changes-802593006.html](https://confluence.atlassian.com/adminjiraserver071/re-indexing-after-major-configuration-changes-802593006.html)