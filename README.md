# Xsolla Login Javascript SDK

Xsolla Login Javascript SDK allows you to integrate Xsolla Login Widget with your website.

Currently SDK supports the following types of authorization:
- via login/password;
- via social networks.

## Requirements

This SDK is used on Windows 7, 8 and macOS.

## Widget Integration

Follow these steps to integrate the widget onto your website. 

1. [Connect](#step-1-connect-xsolla-login-javascript-sdk) Xsolla Login Javascript SDK. 
1. [Add](#step-2-add-the-widget-initialization-code) the widget initialization code. 
1. [Choose](#step-3-choose-a-widget-placing) a widget placing on the website. 

### Step 1. Connect Xsolla Login Javascript SDK

Connect Xsolla Login Javascript SDK:

- **if the project uses Bower.** Launch the console and run the command

```shell script
bower install xsolla-login-js-sdk
```

- **if the Bower is not installed.** Add the following code to the **head** tag of the web page where the widget will be placed
  
```html
<script src="https://cdn.xsolla.net/xsolla-login-widget/sdk/2.1.1/xl.min.js"></script>
```

### Step 2. Add the widget initialization code

Add the widget initialization code to the **body** tag:

```html
<script type="text/javascript">
XL.init({
  projectId: '{Login ID}',
  callbackUrl: '{callbackUrl}'
});
</script>  
```

| Parameter   | Type   | Description                                                                                                                           | Required                                              |
|-------------|--------|---------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| projectId   | string | Login ID from Publisher Account.                                                                                                      | :heavy_check_mark:                                    |
| callbackUrl | string | URL to redirect the user to after authentication. Must be identical to Callback URL specified in Publisher Account in Login settings. | :heavy_check_mark: (if there are several Callback URLs) |

### Step 3. Choose a widget placing

Choose a widget placing on the website:

- [fullscreen mode](#fullscreen-mode);
- [block of page](#block-of-the-page).

#### Fullscreen mode

Add the button with an on-click event and the **XL.show()** function to the website

```html
<button onclick="XL.show()">Fullscreen widget</button>
```

The fullscreen mode will be closed when clicked outside the widget.

#### Block of the page

Add the block with widget to the **body** tag on the page and specify the block ID

```html
<div id="xl_auth"></div>
```

Add the following script and specify the parameters as described below

```html
<script type="text/javascript">
var options = {
  width: 400,
  height: 550
};
XL.AuthWidget(element_id, options);
</script>
```

| Parameter      | Type          | Description                                                                               | Required | Default    |
|----------------|---------------|-------------------------------------------------------------------------------------------|----------|------------|
|     options    |     object    |     Login Widget block settings. The object consists of the parameters listed   below.    | :x:      |     -      |
|     width      |     number    |     Block width in pixels.                                                                | :x:      |     400    |
|     height     |     number    |     Block height in pixels.                                                               | :x:      |     500    |

## Problems

I can’t find Login ID. Where is it?

*Answer*: Please go to your **Publisher Account > Login settings > General settings > Login ID**.

Where can I find the guide described full integration of Xsolla Login?

*Answer*: Please follow the [link to the integration guide.](https://www.google.com/url?q=http://developers.xsolla.com/doc/login&amp;sa=D&amp;ust=1597228765394000&amp;usg=AOvVaw0omWF7PtpIIcvJJ42ArQS6)

