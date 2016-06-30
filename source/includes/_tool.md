# Form Embed Guide

This guide shows how to get form code that will let you build a tool that lets users embed a Wufoo form into your website or application. To do so, we’ll have to circumvent [same origin policy](https://en.wikipedia.org/wiki/Same-origin_policy) for JavaScript calls. We do this with a library called EasyXDM which simplifies cross-domain talking. We encourage you to read [their documentation](http://easyxdm.net/wp/).

## A Simple Example

> A Simple Example

```html
<html>
<body>
    <div id="popup"></div>
    <script src="http://wufoo.com/scripts/iframe/formEmbedKit.js"></script>
    <script>
        var wufoo_framework = WufooFormEmbedKit({'userDefinedCallback':userDefinedCallback, 'displayElement':'popup'});
        wufoo_framework.display();
        function userDefinedCallback(message) {
            alert(message);
            wufoo_framework.destroy();
        }
    </script>
</body>
</html>
```

On our [example page](http://www.wufoo.com/integration/iframe/example/), we present a common use case, how to preview a Wufoo iFrame selected by the user.

 * Line 3 - Defines a div with an ID that corresponds to the second parameter of the function we define on Line 6. This is where our iFrame will appear.

 * Line 4 - Pulls the WufooFormEmbedKit function from our servers

 * Line 6 - Assigns the WufooFormEmbedKit function to the framework object.

 * Line 7 - Calls the initialize function, which opens the Wufoo iFrame

 * Line 8 - userDefinedFunction is created. This does not need to be called userDefinedFunction, but it must match the first parameter in the function defined on Line 6. This function is all yours to define what you want to do with the message parameter when it returns. In our case, we’re simply going to alert it to the screen. In your case, you’re going to do one of two things: 1) concatenate and save the two scripts defined within to your user’s markup 2) preview the form to your user, as explained in our more robust example.

 * Line 9 - Tears down the framework. This closes the iFrame.



## A More Robust Example

First, let’s take a look at how the markup has been set up. The example page (and ultimately your page) is a basic HTML document with a few specially named elements. Let’s look at each.

 * The Button (Fig. 1) - When clicked, you call the method on the object defined in Fig. 8. This action will open the iFrame in the browser.

 * The action-area (Fig. 2) - We’ll be filling this div with a preview of user’s chosen form. This need not be named action-area, but it must correspond to the targetElement parameter of the script call made in Fig. 7.

 * The popup div (Fig 3) - The Wufoo Form Embed Kit will fill this div with the iFrame from which the user will choose the form. The iFrame is fixed at 640x480px.

 > A More Robust Example

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <title>Wufoo Form Embed Kit &middot; Example</title>

    <!--[if lt IE 9]>
    <script src="//html5shiv.googlecode.com/svn/trunk/html5.js"></script>
    <![endif]-->

    <link rel="stylesheet" href="http://wufoo.com/css/iframe/example.css">
</head>

<body>

    <header>
        <h1>Your Awesome Web Application</h1>
    </header>

    <div id="content">

        <div id="actions">
            <ul>
                <li><a href="#">Do something</a></li>
                <li><a href="#">Do something</a></li>
                <li><a href="#">Do something</a></li>
                <li><a href="#">Do something</a></li>
                <!-- FIG. 1 -->
                <li>
                    <a href="#" id="insert-wufoo-form">Insert Wufoo Form</a>
                </li>
            </ul>
        </div>

        <!-- FIG. 2 -->
        <div id="action-area"></div>

    </div>

    <!-- FIG. 3 -->
    <div id="popup">
        <div id="iframe-goes-here"></div>
        <img src="//wufoo.com/images/iframe/demo/fancy_close.png" alt="Close">
    </div>

    <!-- FIG. 4 - The Wufoo Form Embed Kit -->
    <script src="//wufoo.com/scripts/iframe/formEmbedKit.js"></script>

    <!-- FIG. 5 Prototype. You can use jQuery if you like -->
    <script src="//ajax.googleapis.com/ajax/libs/prototype/1.7.0.0/prototype.js"></script>

    <!-- FIG. 6: only required if previewing the form for the user. Add disableForm=true to disable submission in preview -->
    <script src="//wufoo.com/scripts/embed/iframe.js?targetElement=action-area"></script>

    <script>

        //FIG. 7: init the form embed kit  (Warning: Global)
        var wufoo_framework = WufooFormEmbedKit({'userDefinedCallback':userDefinedCallback, 'displayElement':'iframe-goes-here', 'provider':'undefined'});

        //Fig 8: Event listeners, intended to build up and tear down the library.
        $('insert-wufoo-form').observe('click', function() {
            $('popup').setStyle({display:'block'});
            wufoo_framework.display();
            return null;
        });
        // Clicking anywhere outside closes it
        $('popup').observe('click', function() {    
            $('popup').setStyle({display:'none'});
            wufoo_framework.destroy();
            return null;
        });

        //FIG. 9: define a callback, with the required parameters
        function userDefinedCallback(message) {
            //FIG. 10 Close lightbox
            $('popup').setStyle({display:'none'});

            // FIG. 11: MAGIC: Receive code from wufoo.com
            var objMessage = JSON.parse(message);

            // FIG. 12: Create div and write out code for preview
            // You wouldn't necessarily need to preview, you can do whatever you want with the code
            $('action-area').insert(objMessage.display);

            // FIG. 13: tear down the library.
            wufoo_framework.destroy();
        }

    </script>

</body>

</html>
```

###The Script Tags

The example contains three script includes. Let’s discuss what each does.

>Script Tags

```html
FIG. 4 - The Wufoo Form Embed Kit
<script src="//wufoo.com/scripts/iframe/formEmbedKit.js[?debug=true]"></script>

FIG. 5 Prototype. OPTIONAL, we are using for a little helping hand. You can use jQuery, MooTools, whatever... or nothing.
<script src="//ajax.googleapis.com/ajax/libs/prototype/1.7.0.0/prototype.js"></script>

FIG. 6: only required if previewing the form for the user
<script src="//wufoo.com/scripts/embed/iframe.js?targetElement=action-area"></script>
```

 * formEmbedKit.js (Fig 4) - This is the bread and butter. This script is required to make the Wufoo Form Embed Kit work. Without it, bupkis. If you want to see the debugging info provided by your local copy of EasyXDM, add the query parameter debug=true to the end of it. Be aware: this code has not been minimized and logs a lot, which slows your code down, so use only if you’re trying to work out a problem.

 * Prototype (Fig 5) - Not required, but used throughout our example for some help.

 * iframe.js (Fig 6) - This script include is only required if you plan to preview the form on the page for the user. Notice that we pass a GET parameter named targetElement which corresponds to the div defined in Fig. 2. Technically, this prevents the Wufoo iFrame embed snippet from using document.write when placed on the page.

Note the URL’s start with // - that allows those resources to load from HTTP if on a non-secure page or HTTPS if on a secure page. A scheme-relative URL, if you will.

### The Lightbox Effect

We set up two event listeners to handle the click events on the page.

The first event we check for is the clicking of the `<a>` element to open the form. When clicked, we reveal the popup div, which gives the appearance of a lightbox. We also call display on the wufoo_framework object. This opens the Wufoo Form Embed Kit.

We check for a click on the popup. When this happens (the user is done interacting with the iFrame) the wufoo_framework object is destroyed. This removes the iFrame from the page and closes the lightbox effect.

>The Lightbox Effect

```html
//Fig 8: Event listeners, intended to build up and tear down the library.
    $('insert-wufoo-form').observe('click', function() {
        $('popup').setStyle({display:'block'});
        wufoo_framework.display();
        return null;
    });
    // Clicking anywhere outside closes it
    $('popup').observe('click', function() {    
        $('popup').setStyle({display:'none'});
        wufoo_framework.destroy();
        return null;
    });
```

### User Defined Callback

To make this page operational, we must react to the callback. Here’s how that works.

 * Close the Lightbox (Fig 10) - Using prototype, we grab the popup <div> tag and set the CSS selector to display:none. This hides the popup from view. You can get fancy here if you like.

 * Parse the JSON (Fig 11) - At this point, we’re using Douglas Crockford’s json2 (automatically included with the Form Embed Kit) to parse the returned message. If your user’s browser is modern, it will use the built-in JSON parsing call. Otherwise, this the json2 library will be used. Either way, know that the JSON object is safely converted to an object. You can read about this JSON node in the Return Values section of this documentation. For now, know that it contains Wufoo’s Form Embed Snippet for iFrame creation.

 * Append the Embed Snippet (Fig 12) - In order to make the page execute the scripts, you must append it to the DOM using the snippet shown here. We’re appending scripts, using a JavaScript library’s insert method to do so will safely eval them. Most libraries should have some method for this, for instance, jQuery’s append will do it as well.

 * Destroy the Library (Fig 13) - calling framework.destroy() simply removes the iFrame you hid earlier in step 10.

>User Defined Callback

```html
//FIG. 9: define a callback, with the required parameters
function userDefinedCallback(message) {
    //FIG. 10 Close lightbox
    $('popup').setStyle({display:'none'});

    // FIG. 11: MAGIC: Receive code from wufoo.com
    var objMessage = JSON.parse(message);

    // FIG. 12: Create div and write out code for preview
    // You wouldn't necessarily need to preview, you can do whatever you want with the code
    $('action-area').insert(objMessage.display);

    // FIG. 13: tear down the library.
    wufoo_framework.destroy();
}
```

###Return Values

When you set up the User Defined Callback, you provided a message parameter. When the user returns from our iFrame, this parameter will be filled with JSON.

>Return Values

```json
{
    "setup":"<script type="text\/javascript">var host = (("https:" == document.location.protocol) ? "https:\/\/secure." : "http:\/\/");document.write(unescape("%3Cscript src='" + host + "wufoo.com\/scripts\/embed\/iframe.js' type='text\/javascript'%3E%3C\/script%3E"));<\/script>",
    "display":"<script type="text\/javascript">\nvar z7x4a9 = new WufooForm();\nz7x4a9.initialize({\n'userName':'wufooapi', \n'formHash':'z7x4a9', \n'autoResize':true,\n'height':'627',\n'ssl':true});\nz7x4a9.display();\n<\/script>"
}
```

This is simply a JSON object which contains two properties, each containing a `<script>` tag which is ready to be added to your user’s markup. The two properties of this object are as follows.

 * setup - this contains a utility script required to make Wufoo forms appear.

 * display - this is final product: a `<script>` tag which will draw a Wufoo form on your page. We added this script to the page in Fig 12. Based on your user’s account level, the ssl property will be automatically set to true or false.

If you don’t plan on previewing the iFrame for the user, you may concatenate the setup and display and save them for eventual embedding on the user’s page. However, if you’re previewing the form like we do in this example, the setup node must not be included on your page. This is because the setup node has already been written as a script include in Fig 7.

### Register Your Kit

It is free and easy to [register your Wufoo Form Embed Kit](https://master.wufoo.com/forms/register-your-wufoo-form-embed-kit/), and it unlocks some powerful features:

 * Allow for new user signups directly through the kit.
 * Show your logo inside the kit on the login screen.
 * Show your application’s name as the place to return to after a user creates or edits a form on Wufoo.com
