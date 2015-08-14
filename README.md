# twitch-api
Module for easily using all [twitch.tv](http://twitch.tv) API endponits in nodejs

## Installation
`npm install twitch-api`

## Usage

### Step 1: Initialization
```javascript
var TwitchApi = require('twitch-api');
var twitch = new TwitchAPI({
    clientId: 'your client id',
    clientSecret: 'your client secret',
    redirectUri: 'same redirectUri that you have configured on your app'
  });
```

### Step 2: Getting the request code
```javascript
TODO
```

### Step 3: Initialization
```javascript
//TODO: explain code
twitch.getAccessToken(requestCode, function(err, body){
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
Once you have your user's access token, you can use it to query any **authentifcated** resource the user has (and has granted you) access to.

## Methods
