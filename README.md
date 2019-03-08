# PushBird JS
The PushBird JS allows you to invite visitors to subscribe to push notifications. The script should be installed on your website and is linked to your personal PushBird account. 

You can create your own PushBird account [here](https://dashboard.pushbird.com/register)

## JavaScript API
When properly installed, the PushBird JS will be accessible from JavaScript.

### getSubscription
Get the subscription ID from the current visitor. When the visitor has not yet allowed push notifications, the permission will be prompted to the user and when allowed the subscription ID will be returned.

The function will return a promise which will resolve with the subscription ID or rejects when permission are blocked or an error occurs.

#### Example:
```
PushBird.getSubscription().then(function(subscriberId) {
    console.log('Got subscriber ID', subscriberId)
}, function (reason) {
    if (reason === 'messaging/permission-blocked')
        console.log('User has blocked notifications');
    }
    else {
        console.log('An error occurred', reason);
    }
});
```

### subscribe
Promps the visitor to subscribe to push notifications. When the visitor is already subscribed the manage subscription window is displayed.

#### Example:
```
<a href="javascript:PushBird.subscribe()">Subscribe</a>
```
