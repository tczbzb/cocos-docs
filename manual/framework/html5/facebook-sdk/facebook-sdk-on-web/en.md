#Integrate Facebook SDK Beta for Cocos2d-JS on Web

This doc walks you through the integration of Facebook SDK Beta for Cocos2d-JS on Android, including creating app, configuring SDK settings and apk packaging.

Although Facebook has [Facebook SDK for Javascript](http://developers.facebook.com/docs/javascript), if your game has both mobile version and web version, we highly recommend you to use this SDK for the web version because you can use the same code of Facebook integration for both mobile and web without writing them separately for each platform. 

**step1**: Integrate Facebook SDK for Javascript

There are two ways for doing this:

- Option 1: you can find all the files under `frameworks/cocos2d-html5/extenrnal` folder. Then you can load all dependencies manually as below：
    
```
cc.loader.loadJs("", [
    "external/pluginx/platform/facebook_sdk.js",
    "external/pluginx/platform/facebook.js"
], function(){
    //do something
});
```
    
- Option 2: you can directly include Facebook SDK Beta module in `project.json`, the name for this module is `plugin-facebook`. In this way, the engine loads the dependencies in engine's loading process, so it may cause the loading time to be longer.

**step2**: fill out the info of your Facebook App in `project.json` as below,

```
{
    "module" : ["cocos2d", "extensions", "external", "plugin-facebook"],
    "plugin" : {
        “facebook”: {
            "appId" : "", // Your application id provided by Facebook
            "xfbml" : true,
            "version" : "v2.0"
        }
    }
}
```

You can visit [Quickstart: Facebook SDK for JavaScript](http://developers.facebook.com/docs/javascript/quickstart/) to learn more details. 

## How to Use Facebook SDK Beta

Please visit [Facebook SDK Beta for Cocos2d-JS](../api-reference/en.md)
