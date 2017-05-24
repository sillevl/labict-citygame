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

The leaflet map was the hardest object to give it's correct dimensions. Many attempts with CSS were done, but all of them failed. We ended up using the following lines of code in JavaScript. \(Credits to Jasper V. for this\)

```js
$("#map").height($(window).height()/1.427).width($(window).width()/1.56);
map.invalidateSize();

window.onresize = function(event) {
  $("#map").height($(window).height()/1.427).width($(window).width()/1.56);
  map.invalidateSize();
};
```

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

A bug on the controlpanel is present as seen at the bottom of the screenshot. The `<progress> </progress>` is not shown by the footer. The footer is a part of [Foundation's 6.3.1 topbar](http://foundation.zurb.com/sites/docs/top-bar.html "Documentation Foundation Topbar") because we couldn't find a footer provided by Foundation. The footer is not functional when viewed on a smartphone, the tablet version however, does not have this problem.

![](/assets/m.controlpanel1.jpg)![](/assets/m.controlpanel2.jpg)

#### Imageuploader

![](/assets/m.upload.jpg)

#### Maintenance & Game selector/"editor"

##### Disclaimer:

##### Both maintenance and game selector/"editor" are/were not designed for mobile users as it is/was not the intention for an administrator to manage everything from his/her handheld. Managing from a tablet with correct layout is most of the time possible, but not guaranteed.

![](/assets/m.maintenance.jpg)![](/assets/m.game-booking-editor.jpg)

