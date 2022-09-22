
# jira-2-github

👉 This fork contains just some minor modifications, used in our project use-case, to additionaly migrate the Issues's descriptions to Github. 

## Easily Migrate Jira Issues to Github

Export your jira issues as xml and use this app to import them into github issues.

🗣️ *Requires [Github Token](https://github.com/settings/tokens/new) (repo access)*

**Exporting Jira issues**  
Go to jira `issues & filters -> search`, filter out the issues that u want to import into your github project, then export/save as a `xml` file. 

![screenshot](https://raw.githubusercontent.com/lukesUbuntu/jira-2-github/master/export_screenshot.png)




**Importing Jira issues**  
`git clone git@github.com:konsloiz/jira-2-github.git`  

`cd jira-2-github`   

`npm i`  

`npm run build`   

`cd dist`   
 
Edit the config.json and update the required fields:

```
{
    "githubToken": "YOUR_GITHUB_OAUTH_TOKEN",      // https://github.com/settings/tokens/new (requires repo access)   
    "githubUsername": "YOUR_GITHUB_USERNAME",      // github username
    "githubRepo": "YOUR_GITHUB_REPO",              // repo you want to import issues to
    "jiraXmlFile": "FULL PATH TO XML FILE",        // the xml file you exported the issues to
    "dryRun": false                                // test run first to see imported issues
}
```

`node app.js`    

You will get a console.log of what would be imported. If happy, edit the config.json, change `dryRun` to **false** and then run again `node app.js` 
