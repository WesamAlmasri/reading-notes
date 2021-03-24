# Assorted Topics (Audio, Video, Images)

![assorted topics image](https://disenowebakus.net/en/images/articles/audio-video-web-page-internet.jpg)

## HTML Images

Images can improve the design and the appearance of a web page.

Example

```html
<img src="pic_trulli.jpg" alt="Italian Trulli">
```

![html image example](https://camo.githubusercontent.com/86e915bc4716117a80f24f304975ca0c8dc9bda620138ec2df013494f2faab0f/68747470733a2f2f7777772e77337363686f6f6c732e636f6d2f68746d6c2f7069635f7472756c6c692e6a7067)

### HTML Images Syntax

The HTML `<img>` tag is used to embed an image in a web page.

Images are not technically inserted into a web page; images are linked to web pages. The `<img>` tag creates a holding space for the referenced image.

The `<img>` tag is empty, it contains attributes only, and does not have a closing tag.

The `<img>` tag has two required attributes:

- `src` - Specifies the path to the image
- `alt` - Specifies an alternate text for the image

*Syntax*:

```html
<img src="url" alt="alternatetext">
```

#### The src Attribute

The required `src` attribute specifies the path (URL) to the image.

**Note**: When a web page loads; it is the browser, at that moment, that gets the image from a web server and inserts it into the page. Therefore, make sure that the image actually stay in the same spot in relation to the web page, otherwise your visitors will get a broken link icon. The broken link icon is shown if the browser cannot find the image.

#### The alt Attribute

The required `alt` attribute provides an alternate text for an image, if the user for some reason cannot view it (because of slow connection, an error in the src attribute, or if the user uses a screen reader).

The value of the `alt` attribute should describe the image:

```html
<img src="img_chania.jpg" alt="Flowers in Chania">
```

If a browser cannot find an image, it will display the value of the `alt` attribute.

### Image Size - Width and Height

You can use the `style` attribute to specify the width and height of an image.

```html
<img src="img_girl.jpg" alt="Girl in a jacket" style="width:500px;height:600px;">
```

![image size example](https://camo.githubusercontent.com/63947ad2a9fb221e24e275ea21aa3f9d734740a5bbacf81e1f978228133bcfde/68747470733a2f2f7777772e77337363686f6f6c732e636f6d2f68746d6c2f696d675f6769726c2e6a7067)

Alternatively, you can use the `width` and `height` attributes:

```html
<img src="img_girl.jpg" alt="Girl in a jacket" width="500" height="600">
```

### Images in Another Folder

If you have your images in a sub-folder, you must include the folder name in the `src` attribute:

```html
<img src="/images/html5.gif" alt="HTML5 Icon" style="width:128px;height:128px;">
```

### Images on Another Server

Some web sites store their images on another server.

Actually, you can access images from any web address in the world:

```html
<img src="https://www.w3schools.com/images/w3schools_green.jpg" alt="W3Schools.com">
```

## HTML5 video and audio

### Video

The `<video>` and `<audio>` elements allow us to embed video and audio into web pages.

```html
<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>
```

![video](https://camo.githubusercontent.com/fa31507813c3b56d070cb94dc2cb9b798403f9aceb814b81b1613a2783180739/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313237362f302a35746f4a555f495838614f59497a4533)

You can review what all the HTML features do in the article linked above; for our purposes here, the most interesting attribute is `controls`, which enables the default set of playback controls. If you don't specify this, you get no playback `controls`:

![video with no controller](https://camo.githubusercontent.com/1c209216c8f556f90d8953e9b171cd9bf1f32b3df16776b01d5f5f1a7723313b/68747470733a2f2f7777772e627269642e74762f77702d636f6e74656e742f75706c6f6164732f323031382f30372f6272696474762d68746d6c352d766964656f2d706c617965722d332d31323030783637352e6a7067)

#### Implementing the JavaScript

You can control the video using JavaScript by targeting the video element and usign the API to to get access to alot of properties and methods. You can pause, stop, read the timer and so on.

```html
<div class="player">
  <video controls>
    <source src="video/sintel-short.mp4" type="video/mp4">
    <source src="video/sintel-short.webm" type="video/webm">
    <!-- fallback content here -->
  </video>
  <div class="controls">
    <button class="play" data-icon="P" aria-label="play pause toggle"></button>
    <button class="stop" data-icon="S" aria-label="stop"></button>
    <div class="timer">
      <div></div>
      <span aria-label="timer">00:00</span>
    </div>
    <button class="rwd" data-icon="B" aria-label="rewind"></button>
    <button class="fwd" data-icon="F" aria-label="fast forward"></button>
  </div>
</div>
```

```javascript
const media = document.querySelector('video');
const controls = document.querySelector('.controls');

const play = document.querySelector('.play');
const stop = document.querySelector('.stop');
const rwd = document.querySelector('.rwd');
const fwd = document.querySelector('.fwd');

const timerWrapper = document.querySelector('.timer');
const timer = document.querySelector('.timer span');
const timerBar = document.querySelector('.timer div');

play.addEventListener('click', playPauseMedia);

function playPauseMedia() {
  if(media.paused) {
    play.setAttribute('data-icon','u');
    media.play();
  } else {
    play.setAttribute('data-icon','P');
    media.pause();
  }
}
```

### The `<audio>` element

The `<audio>` element works just like the `<video>` element, with a few small differences as outlined below. A typical example might look like so:

```html
<audio controls>
  <source src="viper.mp3" type="audio/mp3">
  <source src="viper.ogg" type="audio/ogg">
  <p>Your browser doesn't support HTML5 audio. Here is a <a href="viper.mp3">link to the audio</a> instead.</p>
</audio>
```

![audio example image](https://camo.githubusercontent.com/3586028bea717f96bad957f82c8cb1f09d3e7c666fb600eecdbedde7cef743e1/68747470733a2f2f6d646e2e6d6f7a696c6c6164656d6f732e6f72672f66696c65732f31323739382f617564696f2d706c617965722e706e67)

#### Restarting media playback

At any time, you can reset the media to the beginning—including the process of selecting the best media source, if more than one is specified using `<source>` elements—by calling the element's `load()` method:

```javascript
const mediaElem = document.getElementById("my-media-element");
mediaElem.load();
```

## Search engine optimization

### Rankings and Traffic Through Search Engine Optimization

#### What is SEO & Why is it Important?

You’ve likely heard of SEO, and if you haven’t already, you could obtain a quick Wikipedia definition of the term, but understanding that SEO is “the process of affecting the visibility of a website or a web page in a search engine's unpaid results” doesn’t really help you answer important questions for your business and your website, such as:

- How do you, for your site or your company’s site, “optimize” for search engines?
- How do you know how much time to spend on SEO?
- How can you differentiate “good” SEO advice from “bad” or harmful SEO advice?

#### Why Should You Care About SEO?

Lots and lots of people search for things. That traffic can be extremely powerful for a business not only because there is a lot of traffic, but because there is a lot of very specific, high-intent traffic.

![search result image](https://camo.githubusercontent.com/e7d796f69487705867c638b2125b60f3d7ddaff0c484ab0f79e811a9eb434e62/68747470733a2f2f776f726473747265616d2d66696c65732d70726f642e73332e616d617a6f6e6177732e636f6d2f733366732d7075626c69632f7374796c65732f73696d706c655f696d6167652f7075626c69632f696d616765732f7468652d6261736963732d6f662d73656f2e706e673f70364658514e7a524c4e4b645f5541646b6e484b30625755386f77786941674f2669746f6b3d61652d396c4c694f)

#### What Actually Works for Driving Traffic from Search Engines?

First it’s important to note that Google is responsible for most of the search engine traffic in the world (though there is always some flux in the actual numbers). This may vary from niche to niche, but it’s likely that Google is the dominant player in the search results that your business or website would want to show up in, and the best practices outlined in this guide will help position your site and its content to rank in other search engines, as well.

![search engines statics](https://camo.githubusercontent.com/86930745a13b83c6f84ce7000f0a2c7a9639f1e842bf2a5e2ba87e562f93e244/68747470733a2f2f776f726473747265616d2d66696c65732d70726f642e73332e616d617a6f6e6177732e636f6d2f733366732d7075626c69632f7374796c65732f73696d706c655f696d6167652f7075626c69632f696d616765732f73656f2d6261736963732d676f6f676c652d6d61726b65742d73686172652e706e673f416b445578694466667849664d7569446f664f7950527668505465676b794a722669746f6b3d7079437364675359)

Google is looking for pages that contain high-quality, relevant information about the searcher’s query.

### On-Page Optimization

Once you have your keyword list, the next step is actually implementing your targeted keywords into your site’s content. Each page on your site should be targeting a core term, and a “basket” of related terms. In his overview of the perfectly optimized page Rand Fishkin offers a nice visual of what a well (or perfectly) optimized page looks like:

![on page potimization image](https://camo.githubusercontent.com/b3438d5302404bec835a65c5ed4d124765d70427de445b07878bf567756dc3bd/68747470733a2f2f776f726473747265616d2d66696c65732d70726f642e73332e616d617a6f6e6177732e636f6d2f733366732d7075626c69632f7374796c65732f73696d706c655f696d6167652f7075626c69632f696d616765732f73656f2d6261736963732d67756964652d706572666563746c792d6f7074696d697a65642d706167652e6769663f634342466367506e435f7a31756e6264687a776b616f34693579343857506c362669746f6b3d386364774247562d)

#### Title Tags

![html title image](https://camo.githubusercontent.com/61fc812e7122ed3b13f8c1fa3c7783979e41d4d6d57feda61f7f03e3c6deaaee/68747470733a2f2f776f726473747265616d2d66696c65732d70726f642e73332e616d617a6f6e6177732e636f6d2f733366732d7075626c69632f7374796c65732f73696d706c655f696d6167652f7075626c69632f696d616765732f73656f2d6261736963732d776861742d69732d612d7469746c652d7461672e706e673f4c743177664c64727a2e4b552e655f6839536b4c444a2e4e33716b546a476f762669746f6b3d317a696d2d584868)

#### Meta Descriptions

![meta info image](https://camo.githubusercontent.com/89e7b02d4939cee60acefcf09f30b42d338f2c91a6de8d1f38183a07ae2b409a/68747470733a2f2f776f726473747265616d2d66696c65732d70726f642e73332e616d617a6f6e6177732e636f6d2f733366732d7075626c69632f7374796c65732f73696d706c655f696d6167652f7075626c69632f696d616765732f776f726473747265616d2d6d6574612d6465736372697074696f6e2d6578616d706c652e706e673f61464773774e7a6c5f4a6f6a714c746a6e45624e717545644130455367464d622669746f6b3d6f67726631765266)

#### Body Content

- Thick & Unique Content
- Engagement
- Sharability

#### Alt Attributes

Filling the `alt` attributes in images element make your image more understandable by search engines.

### URL Structure

Make your url pattern enrichment of keywords. Don't make it contains numbers or anything not related to your topic

#### Schema & Markup

Using a special markups and end elements help the browsers and search engine to recognize the diferent parts of your page like the navigation bar or the main part.

### Summary

- Search engine optimization helps visitors find your sites when using search engines.
- Analytics tools such as Google Analytics allow you to see how many people visit your site, how they find it, and what they do when they get there.
- To put your site on the web, you will need to obtain a domain name and web hosting.
- FTP programs allow you to transfer files from your local computer to your web server.
- Many companies provide platforms for blogging, email newsletters, e-commerce and other popular website tools (to save you writing them from scratch).
