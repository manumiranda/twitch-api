# twitch-api
Module for easily using all [twitch.tv](http://twitch.tv) API v3 endponits in nodejs

## Installation
`npm install twitch-api`

## Usage

Follow the [Authorization Code Flow](https://github.com/justintv/Twitch-API/blob/master/authentication.md#authorization-code-flow) that you can find in the [official twitch.tv API v3 documentation](https://github.com/justintv/Twitch-API):
1. Send the user you'd like to authenticate to twitch.tv's authentication URL (you can get this URL using the convenience method `getAuthorizationUrl` **once the module is initiallized**)
2. If the user authorizes your application, she will be redirected to `https://[your registered redirect URI]/?code=[CODE]`. There you can get the `code` you need to get the user's *access token*.

### Step 1: Initialization
```javascript
var TwitchApi = require('twitch-api');
var twitch = new TwitchAPI({
    clientId: 'your client id',
    clientSecret: 'your client secret',
    redirectUri: 'same redirectUri that you have configured on your app',
    scopes: [array of scopes you want access to]
  });
```

### Step 2: Get the user's access token
```javascript
twitch.getAccessToken(code, function(err, body){
    if (err){
      console.log(err);
    } else {
      /*
      * body = {
      *   access_token: 'your authenticated user access token',
      *   scopes: [array of granted scopes]
      * }
      */
    }
});
```
Once you have your user's *access token*, you can use it to query any **authenticated** resource the user has (and has granted you) access to.

## Methods
