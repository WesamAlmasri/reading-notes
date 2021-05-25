# OAuth (Open Authorization)

![Oauth](https://blogvaronis2.wpengine.com/wp-content/uploads/2012/04/what-is-oauth.png)

## OAuth

**OAuth** is an open-standard authorization protocol or framework that provides applications the ability for “secure designated access.”

**OAuth** stands for "Open Authorization", is a technological standard that allows you to share information between services without exposing your password.

For **example**, you can tell Facebook that it’s OK for ESPN.com to access your profile or post updates to your timeline without having to give ESPN your Facebook password. This minimizes risk in a major way: In the event ESPN suffers a breach, your Facebook password remains safe.

### OAuth 2 implementation

The first step of OAuth 2 is to get authorization from the user. For browser-based or mobile apps, this is usually accomplished by displaying an interface provided by the service to the user.

The first step of OAuth 2 is to get authorization from the user. For browser-based or mobile apps, this is usually accomplished by displaying an interface provided by the service to the user.

- **Authorization Code** for apps running on a web server, browser-based and mobile apps.
- **Password** for logging in with a username and password (only for first-party apps).
- **Client credentials** for application access without a user present.
- **Implicit** was previously recommended for clients without a secret, but has been superseded by using the Authorization Code grant with PKCE.