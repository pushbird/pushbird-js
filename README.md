# PushBird JS
The PushBird JS allows you to invite visitors to subscribe to push notifications. The script should be installed on your website and is linked to your personal PushBird account. 

You can create your own PushBird account [here](https://dashboard.pushbird.com/register)




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
