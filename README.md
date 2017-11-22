How to fire a Facebook Custom Audience pixel after 30 seconds

Normally Facebook Pixel code running when page is loaded. let’s see how to call Facebook Pixel code after sometime.

A normal Facebook re-targeting pixel looks like this:

<script>(function() {
 var _fbq = window._fbq || (window._fbq = []);
 if (!_fbq.loaded) {
 var fbds = document.createElement('script');
 fbds.async = true;
 fbds.src = '//connect.facebook.net/en_US/fbds.js';
 var s = document.getElementsByTagName('script')[0];
 s.parentNode.insertBefore(fbds, s);
 _fbq.loaded = true;
 }
 _fbq.push(['addPixelId', '****']);
 })();
 window._fbq = window._fbq || [];
 window._fbq.push(['track', 'PixelInitialized', {}]);
 </script>
 <noscript><img height="1" width="1" alt="" style="display:none" src="https://www.facebook.com/tr?id=****&amp;ev=PixelInitialized" /></noscript>
 
 
 
 
 
 To make it fire after 30 seconds, use this code instead:
 
 
 <script>setTimeout(function(){ // The setTimeout javascript function will help you fire the JS code after a set amount of time

(function() {
 var _fbq = window._fbq || (window._fbq = []);
 if (!_fbq.loaded) {
 var fbds = document.createElement('script');
 fbds.async = true;
 fbds.src = '//connect.facebook.net/en_US/fbds.js';
 var s = document.getElementsByTagName('script')[0];
 s.parentNode.insertBefore(fbds, s);
 _fbq.loaded = true;
 }
 _fbq.push(['addPixelId', '****']);
 })();
 window._fbq = window._fbq || [];
 window._fbq.push(['track', 'PixelInitialized', {}]);

}, 30000); // 30000 = 30 seconds

</script>
 <noscript><img height="1" width="1" alt="" style="display:none" src="https://www.facebook.com/tr?id=****&amp;ev=PixelInitialized" /></noscript>
 
 
 
 
 
 Be sure to replace “****” with your ID
