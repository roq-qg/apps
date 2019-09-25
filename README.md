# Let's Hack Cancer Apps

Let's Hack Cancer Apps provide functionality to interpret and transform genomic data.

An App is a directory that contains at least a manifest.json file and an executable file. It may contain any number other files, though. 

## The Manifest

The manifest.json has the following structure:

```
{
    "name": "Name of the App",
    "main": "the relative path to the executable file (entry point)",
    "logo": "The app's logo image as a URL",
    "shortDescription": "a textual description of what this app does and maybe who made it",
    "configuration": [{
        "type": "can be either one of `enum`, `text`, `url`, `email`, `boolean` or `tel`",
        "name": "the name that this configuration option's value should be transferred to the app's executable as",
        "label": "The textual label this configuration option should have in the UI",
        "options": [{
            "label": "The display label of the option",
            "value": "the value to be sent to the app's executable",
        }]
    }]
}
```

The optional properties are "configuration" as well as "shortDescription". Everything else needs to be filled. 

## Configuration

The configuration attribute allows the App creator to provide a configuration UI for the user to fill in required options before starting the App. If the attribute is missing from the `manifest.json`, it is assumed that the App provides it's own UI for configuration purposes. In that case, the App is simply embedded as an iFrame into the page. If the configuration attribute exists but is empty, then only a "Run" button will be shown on the UI to trigger the App. 

Given the configuration attribute, the configured information is received by the App from STDIN as a JSON object. Use your programming language's JSON parsing capabilities to access the different configured attributes. Once the app is finished with it's task, it is assumed that the result sent back via STDOUT is another JSON object containing at least the following properties:

```
{
    "type": "can be one of image, text or csv",
    "url": "the URL to the image generated",
    "content": "the text generated or the CSV content as a string".
}
```

Of this response object, the `url` property is optional, if the type is not `image`.

## Deployment

When deploying an App, make sure that all dependencies are included. For Python, add a corresponding setup.py file. For NodeJS scripts, add a package.json. By pushing the App into this repository's master branch, it will be automatically deployed on the server. Due to this, no direct pushing is allowed. For a new app, please create an app branch with the following naming scheme: `app/<name-of-the-app>` (whereby `<name-of-the-app>` is replaced with the respective normalized app name). 

Once the app has been developed, create a pull request to have it merged into the master branch. Creating a pull request allows the code to be reviewed. If the code review reveals any items that need to be fixed, the pull request will need to be updated (by pushing the respective changes to the app's branch). Once the pull request is approved, it will be merged into the master branch an be live.
