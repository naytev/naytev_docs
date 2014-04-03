---
title: API Reference

language_tabs:
  - html
  - php
  - ruby

toc_footers:
  - <a href='http://www.naytev.com'>Go back to NAYTEV</a>

includes:
  - errors

---

# Introduction

Welcome to the NAYTEV documentation. In just a few minutes (usually under 5), we'll have you running experiments on your website.

All you have to do to integrate NAYTEV with your existing share buttons is add one line of code to your website to include the NAYTEV javascript library.

If you don't already have share buttons, we'll add those too (they are also just a single line of code). NAYTEV is compatible out of the box with about 95% of existing share buttons across the web, so chances are we'll work with your existing ones if you have them.

# Create a Facebook App

> You need a Facebook App because Facebook requires shares to come from an app's authorized domain.

If you already have your Facebook App ID, you can skip to the next section. You can find your Facebook App ID in your Facebook Developers dashboard (more info below).

1. Login to Facebook with the account you normally use. 
1. Visit <a href="http://developers.facebook.com" target="_blank">Facebook's Developers Page</a> (if prompted, accept the Terms of Service) 
1. On the top left, click the “Apps” dropdown,  and select “Create New App” ![createapp](facebook/createApp.png)
1. Give your App a name (your users will see this name when they Share) and choose the category “Apps for Pages” 
1. On your new App Dashboard, copy the App ID as you will need it in the next section. ![createapp](facebook/appID.png)
1. On the left, navigate to the “Settings” tab. Enter your website’s address in “App Domain”, your email address in “Contact email”, and then click “Add a Platform” ![createapp](facebook/addPlatform.png)
1. Select “Website” ![createapp](facebook/website.png)
1. Enter your website’s information, then click Save. Note: It’s important that the site you enter here matches the site where your users will be sharing. For security purposes, shares the don’t match will be ignored. ![createapp](facebook/websiteDetails.png)
1. Activate your app.  On the “Status & Review” tab, change toggle button indicated by the red arrow on the right from “No” to “Yes”. ![createapp](facebook/activate.png)
1. You’re good to go! Head over to NAYTEV and you can start using your shiny new app immediately. 

<aside class="notice">
The domain (website) of your Facebook App must match the site you're installing NAYTEV on. This is a security measure, and experiments will be ignored when the domain doesn't match.
</aside>

# Create a NAYTEV Account

1. Sign up and login to your NAYTEV dashboard so that you can connect Your Domain.

2. Click "Create a Site" and add your first site. You can have multiple sites with NAYTEV, but you'll add them one at a time.

3. Using your Facebook App ID from the previous step, enter your website's information:
  * Domain
  * Facebook App ID
  * (Optional) Redirect URL

4. The system will give you a unique, custom code to embed in your website (see next step).

<aside class="notice">
Your redirect URL is the URL that you momentarily direct a site visitor to after they have completed a social share using a social share button. For example, a visitor shares your content, and then immediately sees a custom message such as “Thanks for Sharing”, which may disappear after a second. The Redirect URL is what contains the “Thanks for Sharing” message. Using a Redirect URL is not required. You can determine if your organization uses a Redirect URL by contacting your website administrator.
</aside>


# Installation

> No matter what language you use, the goal is to put your unique NAYTEV javascript code in the <head> section

```html
#Simply copy and paste the script exactly as it appears into the <head> section of your website. The numbers in your script will be different.

<script src='http://cdn.naytev.com/js/embed/123456789123456789.js'></script>

```

```php
# In Drupal, you'll want to do something like this inside the template.php file:

drupal_add_js("your NAYTEV Javascript URL that you copied here", 'external');

#example: 

drupal_add_js("http://www.naytev.com/js/embed/53284cs394ds32f2f960532f5.js", 'external');

```

```ruby

<%= javascript_include_tag "http://www.example.com/xmlhr.js" %>

```


Now that you have your NAYTEV embed code, it's time to add it to your website. Your code will look similar to this:

`<script src='http://cdn.naytev.com/js/embed/123456789123456789.js'></script>`

<aside class="notice">Your numbers will be different, as they are unique to your account/website.</aside>

**This code needs to be present in the &#060;head&#062; section of every page you'd like to run experiments.** 

For Wordpress and Drupal, refer to the PHP instructions. Additional information for [Wordpress](https://codex.wordpress.org/Using_Javascript) here.

# Add Share Buttons

> Compatible share buttons, if you need them, can be added anywhere by adding a div with the data-naytev-share attribute

```
<div data-naytev-share></div>

```

While NAYTEV works with almost all existing share buttons, not all sites have them to begin with. Luckily, we're ready to make that process simple and easy as well. That one line of javascript you added earlier also has the capability to create a button anywhere on your site.  

Simply add the folowing code anywhere you'd like a button to appear:

`<div data-naytev-share></div>`

Buttons generated with the NAYTEV data attribute will look like this: 

![naytevbutton](naytevbutton.png)

<aside class="notice">
  Any other form of integration will NOT affect the look or feel of your buttons, allowing you to add experiments without changing your design. Any buttons that do not have experiments tied to them will continue to work as normal.
</aside>

We work out of the box with AddThis and Sharethis:

![naytevbutton](addthis.jpeg)    ![naytevbutton](sharethis.png)


