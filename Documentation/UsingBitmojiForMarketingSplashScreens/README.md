**Using Bitmojis for Marketing/Splash screens**

We recommend using the LOD0 (high poly models with PBR materials) Bitmojis for marketing materials, splash screens for games and/or anywhere you need pre-rendered images of Bitmojis.

This models can be imported into Blender/Maya and the rig can be found on the [Bitmoji for Games GitHub repo](https://github.com/Bitmoji/BitmojiForGames/tree/master/Documentation) for posing.

As they use PBR materials, please use Image Based Lighting (IBL) with a skybox for the best quality render.

Below is a temporary method to get the LOD0 Bitmoji while we create a more formal tool/app for this:

1.  Open the PlayCanvas Bitmoji with Snapkit app: https://playcanv.as/e/p/LwHJVHP5/
2.  Click on the yellow button in the top left 'Continue with Snapchat' and sign in
3.  After signing in, open the browser devtools and click on the 'Console' tab![mceclip1.png](images/mceclip1.png)
4.  At the bottom, type the following, where XXXXXXXXXXX is the Avatar ID either from the [NPC list](https://github.com/Bitmoji/BitmojiForGames/tree/24dff85d97039c87b547ec2c64f35092b0b1d288/Documentation/NonPlayerCharacters) or the Avatar ID from a Bitmoji created in the Bitmoji creator tool. Press enter to start the download.

    downloadAvatar3dLod0('XXXXXXXXXXX')

    To download the LOD0 version of the Bitmoji that is signed in, you can call the function without the Avatar ID. This can make it easier to get Bitmojis without needing to find the Avatar ID ie:

    downloadAvatar3dLod0()

    ![mceclip2.png](images/mceclip2.png)
5.  A GLB file will be downloaded (you may have to wait a little bit) that will have the LOD0 Bitmoji. This can be checked with the [PlayCanvas Viewer Tool](https://playcanvas.com/viewer) ![mceclip3.png](images/mceclip3.png)
