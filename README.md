# todayAtWork


Remember those books we bought in kids that were like **The Games Bible** where you had all the *cheats, tricks and missions* of a game solved? 
I want this repo to be like that but for **problems people have been finding all over the years developing web apps**.

It's a repository where I will be posting the problems and sugestions I found everyday at work and its solutions or fixes. 
It may be a real problem solution or a simple trick or note. Every problem, fix or tip will be posted as a *day* just because.

If you want to contribute with tips and fixes, feel free!

(As you will see, there is a lot of markdown here, I'm using the [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) from adam-p, I think it is pretty known but it's always worth to mention and to say thanks) 

I'm pretty sorry for all the typos and grammar errors, feel free to correct them as one of this repo objectives is to improve my english too.

### Major topics:
- JavaScript
- CSS
- Phonegap

[Day 1 - Croping the center of an image with canvas](days/1.md)

[Day 2 - input type=file sugesting opening vídeo camera in Android](days/2.md)
### Problem (accept and capture tags)
We have implemented the file upload at my job, and we're a Phonegap App so we have to implement the file upload through the input tag. 
I found that Android and iOS phones have a "upload files dialog" which automatically sugests to open the file browser or the camera. The camera one is a very cool feature as it automatically takes the pic and attaches it to our input type file.

**Problem:** The suggested camera was the **video camera**, that obviously isn't what we were expecting. Searching the web for some minutes I found this [link](https://www.w3.org/TR/html-media-capture/#the-capture-attribute). 
It explains the **accept** attribute where you can specify the **MIME** types you want for file uploading, which was the fix I needed. 
It also mentions the **capture** attribute which should automatically open the camera but as far as I know the behaviour is not consistent across browsers.

``` html
<input type="file" name="image" accept="image/*" capture>
```

[Day 3 - Javascript code documentation](days/3.md)
### Sugestion (JSDOC and SpeakingJS)
At my job we have some Javascript code (a phonegap App and Desktop one) and the two are **Backbone based**, using the [Backbone Generator](https://github.com/yeoman/generator-backbone) from [Yeoman](https://github.com/yeoman) with **RequireJS** and **SASS**. 
As you can expect, the code is not as documented as I expected and at the moment that is not a problem. The problem is when you have to introduce a new developer to the code.

You have to choose one of two possibilities:
- Let the developer bang his head on the walls for two weeks
- Take a lot of time introducing the new developer to the code and be available to answer a lot of questions for weeks

As I'm tired of answering questions and seeing my colleague banging with his head I obviously decided to gradually start documenting our code. I knew about **JSDoc** in [SpeakingJS](http://speakingjs.com/) which is a very well written book about JS, I've not read the whole book but I read some chapters and only have good things to say about it. 
I will be posting here problems and tricks to work with **JSDoc**.

The script below, is in the [SpeakingJS](http://speakingjs.com/), and I'm only pasting this here to illustrate what JSDoc is
``` javascript
/** @namespace */
var util = {
    /**
     * Repeat <tt>str</tt> several times.
     * @param {string} str The string to repeat.
     * @param {number} [times=1] How many times to repeat the string.
     * @returns {string}
     */
    repeat: function(str, times) {
        if (times === undefined || times < 1) {
            times = 1;
        }
        return new Array(times+1).join(str);
    }
};
```

