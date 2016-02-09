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

## Twitter

Twitter sharing is way easier than Facebook

### Step 1

```javascript
//These are variables because in real life, you'll likely automatically create these elsewhere in your app.
var share_url = 'http://whatever.com';
var share_text = 'Your share text with marketing speak in it, preferably.';

var url = 'http://twitter.com/share?url=' + share_url + '&text='+share_text;

```
### Step 2

```javascript

function openWindow(url) {
    let winWidth, winHeight;

    winWidth  = 600;
    winHeight = 400;

    var winTop  = (screen.height / 2) - (winHeight / 2);
    var winLeft = (screen.width / 2) - (winWidth / 2);
    var w       = window.open(url, 'sharer', 'top=' + winTop + ',left=' + winLeft + ',toolbar=0,status=0,width=' + winWidth + ',height=' + winHeight);

    return (!w); // opens in new window/tab if allowed

}

    //something on click...
    
    openWindow(your_url_from_step_one);
```

## Tumblr

Similar to Twitter. Example below is for posting a photo, buit you can change the posttype param to one of the other types,

### Step 1

```javascript
//These are variables because in real life, you'll likely automatically create these elsewhere in your app.
var share_url = 'http://whatever.com';
var share_text = 'Your share text with marketing speak in it, preferably.';
var share_title = '';
var tumblr_url = 'https://www.tumblr.com/widgets/share/tool?CanonicalUrl=&url='+share_url+'&posttype=photo&title=' + title + '&caption=' + text+ '&content=' + short_photo_url;

```
