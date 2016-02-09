# Below is a collection of share methods for various social networks. I plan to add to this. Pull requests welcome.

## Facebook
* Note Facebook requires a 'live' URL for this to work correctly. You can use locahost as your app URL and domain during dev, though

### Step 1 - get a Facebook App ID @ https://developers.facebook.com/

### Step 2

Insert your FB js SDK code in your doc

```javascript

window.fbAsyncInit = function () {
    FB.init({
        appId  : '<your Facebook app id>',
        xfbml  : true,
        version: 'v2.5'
    });
};

(function (d, s, id) {
    var js, fjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) {
        return;
    }
    js     = d.createElement(s);
    js.id  = id;
    js.src = "//connect.facebook.net/en_US/sdk.js";
    fjs.parentNode.insertBefore(js, fjs);
}(document, 'script', 'facebook-jssdk'));

```

### Step 3

In your JS code, call the FB.ui method:

```javascript

 FB.ui({
    method     : 'feed',
    link       : 'http://your-url-here.com',
    name       : 'Share title',
    description: 'Share description, yadda',
    picture    : 'http://image-url-here.com'
}, function (response) {
  
  //Do something with the response

});

```
