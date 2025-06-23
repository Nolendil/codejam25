# Hanging with our crow friend!
# A pseudo-captcha for the Kitboga's CodeJam 2025

[Try it now!](https://nolendil.github.io/codejam25/)

## Foreword

Try it before reading further, it's more fun if you don't know what's going on.

## How to ~~play~~ pass the totally legit human test
Try letters and guess the secret word!
Entering letters can be done by using a keyboard or, if you're on a phone, by clicking the virtual keyboard (which is conveniently ordered in alphabetical order, as it should 😁).
Wrong letters are displayed in green on the keyboard, correct ones appear red, to shake up the traditional conventions.
Entering a wrong letter makes you lose a life. Lose all lives and it's game over. But don't feel bad, you can always try again. We'll even give you more lives, up to 26 to make sure you will eventually succeed and feel good about yourself.

## What is going on? (SPOILERS!)

This is like a Hangman game, except it's **very** unfair.
The secret word is not chosen at the start. Instead, the game starts with a list of about 500 words and everytime you enter a letter, it tries and discards all words that contains your chosen letter.
A letter is accepted only when it's present in all the remaining words.
It's most likely impossible to win with less than 8 lives.
You can try and start with "E-T-A-O-I-N", the most common English letters, to reduce the pool of candidate words fast.
However, the fastest way to pass the test is probably to spam inputs and retry until you eventually win.

Also, your helpful crow friend gives you a usefull hint... composed of random unicode characters.

## Adjusting difficulty
- Two lists of words are provided: 4 or 5 letter words. Set the variable `wordLength` to 4 or 5 to choose one or the other. Counterintuitively, games using longer words should be easier since candidate words are more likely to be eliminated on each attempt.
- Number of starting lives can be adjusted with the `attempts` variable.
- How many extra lives you get at each attempt can be adjusted with the `attemptMultiplierOnRetry` variable.

## Debugging
Change the `bDebug` variable to display/hide some debug information:
- Number of possible words (and displaying the full list when there's 10 or less)
- Correct and wrong letters entered in order

## Possible future improvements:
- ✅ ~~Add feedback in the crow bubble about the letter being wrong or correct.~~
- 🚧 Switching to use the Public Domain word list from [MichaelWehar](https://github.com/MichaelWehar/Public-Domain-Word-Lists/blob/master/5000-more-common.txt), it has a good number of 4+ letter words and seems SFW.
- Add a random chance that a letter is accepted, to make the mechanics more confusing.
- Redraw the background to have bigger speech bubble (or leave it like that because it's janky?)
- Spawn flying beans that the user need to click for a "super" bonus. E.g.
  - do nothing
  - give an extra life
  - make the crow eyes glow
  - increase chances of accepting a letter...

## Credits
- The crow image was edited from this [CC0 Public Domain photo](https://www.publicdomainpictures.net/en/view-image.php?image=300612) taken by [Circe Denyer](https://linktr.ee/circod).
- Lists of words were taken from [copylists.com](https://copylists.com/words/). I suppose they are free to use but couldn't find a clear statement on the site. (NB: "green" is rightfully not on the [list of creative words](https://copylists.com/words/list-creative-words/))



**Original ReadMe below:**

---

# Kitboga Code Jam
"I'm not a robot!"

This GitHub repository contains a template you should fork, modify to include your captcha, and then submit to us. Please read all the information in this readme before getting started!
**The deadline for submissions is 27th June 2025!**

## Rules
1. Follow the guidelines in `captcha/captcha.html` as to where and how your code should be written.
2. It goes without saying, but no malicious code. We want to frustrate and anger scammers, but it's no fun if we just crash their browser, and we're not interested in doing anything illegal. Specifically:
    - No resource-hogs
    - No crypto mining
    - No fork bombs or similar
    - No attempting to reveal their personal information
    - No exploits
    - No payload deployment
    - No attempts to collect or display personal information
3. Please try to match the tone of the Kitboga community. You are very unlikely to be selected if your submission contains:
    - Bad language (this will spook a scammer right away)
    - Racism, or basically any other -ism
    - Vulgarity or anything NSFW
    - Anything which would violate the Twitch or YouTube TOS. If you are unsure where this line is, then better to stay on the safe side.
4. Please don't use copyrighted logos or brand names in your submission. If you have an idea for something incredible which only works with a particular brand, check with us in Discord.
5. No obfuscation. If we can't read or understand the code, we're probably not going to run it.
6. No requests for resources outside of your repository, except for well-known javascript libraries from a CDN (jsdelivr, unpkg, googleapis, etc). Aside from these, include all the assets you need in your repository, such as fonts, icons and everything else. If you have a specific idea which requires access to the Internet, perhaps to fetch live stock market data for example, then try to fake it. If it's important to you to make external requests, talk to us about it in Discord.
7. When submitting your code, please tell us about every feature, even "easter eggs". No surprises!
8. WebAssembly and Web Workers are not allowed.
9. Do not include minified code; this includes code generated from build tools like Vite (see also [disabling minification](https://vite.dev/config/build-options#build-minify)) or WebPack. Prefer not using any build tools, if possible.
10. Do not increase the size of the captcha, as it will be embedded in an iframe of the specific size 390px * 300px.

## Discord
Please feel free to join the Kitboga discord, and hang out in the #code-jam channel. That's a great place to ask for help, and it will be useful if we need to contact you about your submission for whatever reason.
https://discord.gg/kitboga

## Getting Started
1. Create a GitHub repository from the template: https://github.com/new?template_name=codejam25&template_owner=The-Kitboga-Show
2. Clone the new repository locally to your machine
3. Open the "game shell" in your browser; this can be done in 2 ways:
   - By opening `index.html` directly in your browser
   - By running a local webserver (this can help with testing on different devices too). One easy way to do this, if you have python installed, is to run this command in the terminal: `python3 -m http.server 8000`. Then open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser (the port may vary if you used a different method to start a web server).
4. Create your game in `captcha/captcha.html`! All parts of your submission should be in the `captcha/` folder.
5. Commit and push your changes
6. See the "How to Submit" section below

## Advice
1. Scammers are often using iPhones, so make sure your CAPTCHA works properly in that format. They also use desktops, usually with Chrome or Edge, so it's a good idea to make sure it works well in a desktop format also. (See also [device mode on Chrome](https://developer.chrome.com/docs/devtools/device-mode/), or [responsive design mode on Firefox](https://firefox-source-docs.mozilla.org/devtools-user/responsive_design_mode/).)

2. The best submissions will be ones which are fun to watch, and also irritating for the scammer. They should be designed so that the scammer finds them difficult or confusing to complete, but they should eventually be completable, within around 5 minutes. Having some element of skill (rather than only chance) is more likely to keep a scammer hooked and actively trying to pass your CAPTCHA.

3. If you want to go the extra mile, having some configuration in the code which increases or decreases the difficulty could be a nice touch.

4. We will prefer human-generated content. Feel free to use some AI during development, but don't just ask it to come up with and create an idea.

## Forbidden APIs and functions
Please don't use any of the following:
- navigator.geolocation
- navigator.getUserMedia()
- navigator.connection
- navigator.clipboard
- navigator.bluetooth
- navigator.usb
- navigator.serial
- navigator.requestMIDIAccess
- window.showOpenFilePicker()
- window.showSaveFilePicker()
- navigator.serviceWorker
- window.open()
- window.print()
- navigator.permissions
- navigator.credentials
- RTCPeerConnection
- fetch, XMLHttpRequest, WebSocket, etc.

## Examples
- [Crow Lifting Weights](https://courageousmayonnaise.github.io/codejam25-crow-lifting-weights/) ([source](https://github.com/CourageousMayonnaise/codejam25-crow-lifting-weights))
- [Scratch Off Game](https://courageousmayonnaise.github.io/codejam25-scratch-off/) ([source](https://github.com/CourageousMayonnaise/codejam25-scratch-off))
- Anti-Example: [Cube Game](https://courageousmayonnaise.github.io/codejam25-cube-game/) ([source](https://github.com/CourageousMayonnaise/codejam25-cube-game))
  - *Why is this an anti-example?* This game uses copyrighted material and is not an original creation. It also lacks a clear solution.

## Prizes and Judging
Entries will shortlisted by a panel of Kitboga Show team members, and will be judged subjectively based on originality, technical merit, entertainment value and style. The best will go forward to a final round where they will be tried with scammers live on-stream. There may be prizes, including things such as merch, signed items, and gift cards.

## How to submit
**Remember, the deadline is 27th June 2025!**
Don't forget to read the license in TERMS.md, which you'll need to agree to in order to take part.

Go here: https://kitboga.com/codejam

## (Optional) Live Demo
Add a publicly viewable demo for your CAPTCHA by enabling GitHub Pages in your repository settings. Navigate to `Settings` > `Pages`, then under `Branch`, select `main`, and then press `Save`. Once the site is built the URL will appear.

## Further help
Drop into the Kitboga discord server, and check out the #code-jam channel. Please don't ask questions via email, as we might not see them before the deadline.
