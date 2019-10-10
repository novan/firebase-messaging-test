# Firebase Cloud Messaging
This is a simplified version of firebase messaging example.

## Running
1. You must have the Firebase CLI installed. If you don't have it install it with `npm install -g firebase-tools` and then configure it with `firebase login`.
2. On the command line run `firebase use --add` and select the Firebase project you have created.
3. On the command line run `firebase serve -p 8081` using the Firebase CLI tool to launch a local server.
4. Open [](http://localhost:8081) in your browser.
5. Click **REQUEST PERMISSION** button to request permission for the app to send notifications to the browser.
6. Use the generated Instance ID token (IID Token) to send an HTTP request to FCM that delivers the message to the web application, inserting appropriate values for `YOUR-SERVER-KEY` and `YOUR-IID-TOKEN`.

## Testing
Run this on your terminal:
```
curl -X POST -H "Authorization: key=YOUR-SERVER-KEY" -H "Content-Type: application/json" -d '{
  "notification": {
    "title": "Portugal vs. Denmark",
    "body": "5 to 1",
    "icon": "firebase-logo.png",
    "click_action": "http://localhost:8081"
  },
  "to": "YOUR-IID-TOKEN"
}' "https://fcm.googleapis.com/fcm/send"
```
