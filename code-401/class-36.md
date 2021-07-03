# Application State with Redux

![Application State with Redux](https://i.morioh.com/200725/046f040f.webp)

## Review, Research, and Discussion

1. What are the advantages of storing tokens in “Cookies” vs “Local Storage”

Cookies are automatically saved, sent and removed by the browser. When doing browser level navigation, only cookies are sent. Sharing the same session across subdomains can easily be done with cookies. Cookies have a special flag called httpOnly, which means that malicious JS code cannot send the access token to the attacker.

2. Explain 3rd party cookies.

Third party cookies are cookies that are set by a website other than the only you are currently on. For example, a "Like" button on a website which will store a cookie on a visitor's computer, that cookie can later be accessed by Facebook to identify visitors and see which websites were visited. Such a cookie is considered to be a 3rd party cookie. 

3. How do pixel tags work?

racking pixel or pixel tag (also called 1x1 pixel) is a graphic with dimensions of 1x1 pixels that is loaded when a user visits a webpage or opens an email. The website operator or sender of an email adds the tracking pixel using a code in the website’s HTML code or email. This code contains an external link to the pixel server. If a user visits the destination website, the HTML code is processed by the client – usually the user’s browser. The browser follows the link and opens the (invisible) graphic. This is registered and noted in the server’s log files. In addition, various information about the user is also transmitted using this method. To some extent, combination with JavaScript is necessary in order to collect information about the operating system or browser type. The following data can be acquired and analyzed with a tracking pixel: operating system used, type of website or email used (mobile or desktop), type of client used (browser or mail program), client's screen resolution, time the email was read or website was visited, activites on the website during the session (when using multiple tracking pixels), IP address.

## Terms

- **Cookies**: small bit of data stored on a user's computer by the web browser while browsing a website, designed to be reliable mechanism for websites to remember stateful information or to record the user's browsing activity

- **Authorization**: Process of giving someone the ability to access a resource 

- **Access Control**: Component of data security that dictates who is allowed to access and use company information and resources. Through authentication and authorization, access control policies make sure users are who they say they are and that they have appropriate access to company data.

- **Conditional Rendering**: The ability to render different user interface (UI) markup if a condition is true or false. In React, it allows us to render different elements or components based on a condition.

## Dan Abramov Redux Tutorials

- Everything that changes in an app is stored in a single object
- Action allows for changes to Redux
- State is redundant
- Redux functions must be pure
- Function must take in previous state and return the new state
