<h1>Using Bitmoji Stickers</h1>


The Snap Kit SDK allows you to fetch a user’s 2D Bitmoji through _sc.fetchAvatar2D_. This method enables your users to download their Bitmoji selfies and express their emotions through their 2D avatar. You can also utilize Bitmoji stickers in a more advanced manner. Since your users are already authenticated, you can take advantage of our Bitmoji Direct stickers API to fetch more expressive, full-body stickers for your users.


<h3>What is Bitmoji Direct?</h3>


Bitmoji Direct offers an easy way to create personalized experiences using Bitmoji. You can create custom URLs using avatars and stickers from the Bitmoji collection. The format of these URLs are as follows:

**Bitmoji Sticker ― current player**


```
GET https://sdk.bitmoji.com/me/sticker/<avatar_id>/<sticker_id>
```


**Bitmoji Sticker ― current player’s friend**


```
GET https://sdk.bitmoji.com/me/sticker/<avatar_id>/<sticker_id>?friend=1
```





<table>
  <tr>
   <td><strong>Example Bitmoji Sticker ― current player:</strong>
<p>
https://sdk.bitmoji.com/me/sticker/<strong>AVZua</strong>
<p>
<strong>0OIHP5fRYeKRn4XJ2jVU8Gs/fdf25fcb-3911-491f-89e6-208a85dfd21f</strong>
   </td>
   <td><strong>Example Bitmoji Sticker ― player’s friend:</strong>
<p>
https://sdk.bitmoji.com/me/sticker/<strong>AVZua</strong>
<p>
<strong>0OTr_lYm6vbUhuX7_iwbyvn/7218c89b-a039-4a96-bab6-67c159880d85?friend=1</strong>
   </td>
  </tr>
  <tr>
   <td>

<img src="images/fdf25fcb-3911-491f-89e6-208a85dfd21f.png">

   </td>
<td>
<img src="images/7218c89b-a039-4a96-bab6-67c159880d85.png">

   </td>
  </tr>
</table>




<h3>How to Locate the IDs</h3>


To populate the Bitmoji Direct URL described above, you will need an avatar ID and a sticker ID.

<h4>Avatar ID</h4>


An avatar ID can be one of the following:



1. The avatar ID of the current player ― sc.app.user.avatarId
2. The avatar ID of the player’s friend ― sc.app.user.avatarId?friend=1

 **Sticker ID**

We currently do not have a self-serve tool available for obtaining sticker IDs, so the process is somewhat cumbersome. To obtain a sticker ID, you will need to fetch them manually and hard-code them into your game. In order to achieve this:



1. Download our [Bitmoji Chrome Extension](https://chrome.google.com/webstore/detail/bitmoji/bfgdeiadkckfbkeigkoncpdieiiefpig).
2. Search through the Chrome extension to find a Bitmoji sticker that you like.
3. Then, copy that image's URL, paste it into your browser's address bar, and navigate to it. The sticker should be displayed in your browser.
4. The sticker ID will be included in that URL. The easiest way to fetch it is to copy and run the following Javascript code in your browser console, in the tab where you navigated to the sticker's URL:


```
javascript:var
stickerId = window.location.href.split('/')[5].substring(0, 36);
alert("The stickerId is " + stickerId);
```


Now, you can use the avatar ID and sticker ID to build your URL. Please remember to add sdk.bitmoji.com to your CSP allow list.
