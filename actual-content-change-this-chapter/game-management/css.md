# CSS

## Results

### Chrome on desktop

#### Homepage

![](/assets/homepage.jpg)

#### Bookingpage

![](/assets/booking.jpg)

#### Scorepage

#### ![](/assets/scores.jpg)

#### Aboutpage

![](/assets/about.jpg)

#### Loginpage

![](/assets/login.jpg)

#### Controlpanel

![](/assets/controlpanel.jpg)

#### Imageuploader

![](/assets/upload.jpg)

#### Maintenance

![](/assets/maintenance.jpg)

#### Game selector/"editor"

![](/assets/editgame-booking.jpg)

### Chrome on mobile \(Android\)

#### Homepage

![](/assets/m.homepage.jpg)

#### Bookingpage

![](/assets/m.booking.jpg)

#### Scorepage

![](/assets/m.scores.jpg)

#### Aboutpage

For our aboutpage, we've included an `<iframe>` with the content of the GitBook. Many attempt were made with CSS to resize the iframe but we ended up using JavaScript. Window is resized with this code below.

```js
$( document ).ready(function() {
  if(window.location.pathname == "/about") {
    console.log("iFrame sizing should be executed");
    function scaleIframe(){
      window.updateIframe = function() {
        var h = $(window).height();
        $("#iframe").height(h-56);
      }
      window.updateIframe();
    }
    $(window).resize(scaleIframe);
    $(window).onload = scaleIframe();
    console.log("iFrame sizing was executed");
  }
});
```

#### Loginpage

![](/assets/m.login.jpg)

#### Controlpanel



#### Imageuploader

![](/assets/m.upload.jpg)

#### Maintenance & Game selector/"editor"



