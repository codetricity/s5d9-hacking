Medium One has the source code for their Diagnostics Intelligence project and and the Board Support Package file in their [GitHub repository](https://github.com/Medium-One/diagnostics-intelligence-s5d9). This source code is for building a `.srec` that uses the factory bootloader on the board. The `Put binary here` folder.



##  How to Build Medium One Diagnostics Intelligence 

## Updating Components
The code requires SSP v1.2.1 ([download](https://synergygallery.renesas.com/ssp/package#read)). I'm updating my SSP from v1.2.0 to v1.2.1

[![](img/diagnostics-intelligence/ssp.png)](https://synergygallery.renesas.com/ssp/package#read)

The SSP v1.2.1 requires e2 studio 5.4.0.018 or later. I'm also upgrading e2 Studio ([download](https://synergygallery.renesas.com/isde)).

I next downloaded the Medium One Cloud Agent for Synergy SSP 1.2.x installed. ([download](https://synergygallery.renesas.com/addon))

![](img/diagnostics-intelligence/m1cloud.png)

## Download Code From GitHub

I'm  using git from the command line using git bash on Windows 10. You can also download the zipped project from GitHub and extract the contents.

![](img/diagnostics-intelligence/gh.png)


## Extract Medium One Cloud Agent

![](img/diagnostics-intelligence/extractCloud.png)

I extracted the Medium_One_Cloud_Agent_and_Demo into the `m1` folder. I'm leaving the m1-20161103 file zipped.

## Move IOT Board Pack into e2 Studio

Assuming you installed e2 Studio into the default location, look for 

    C:\Renesas\e2_studio\internal\projectgen\arm\Packs

![](img/diagnostics-intelligence/bsp.png)

## Import Project Into e2 Studio
After you start e2 Studio, go to File -> Import

![](img/diagnostics-intelligence/import.png)

Select *General*

![](img/diagnostics-intelligence/general.png)


Select *Rename & Import Existing C/C++ Project into Workspace*

![](img/diagnostics-intelligence/existingProject.png)

Select root directory. Browse to the folder that contains the diagnostics intelligence project you downloaded from GitHub.

![](img/diagnostics-intelligence/root.png)

Click Finish.

![](img/diagnostics-intelligence/root.png)

You will see a popup in the lower right corner indicating *Synergy License Required*.

![](img/diagnostics-intelligence/licenseRequired.png)

Set up the license. 

Browse for the License file.

![](img/diagnostics-intelligence/licenseBrowse.png)

Press *Browse* again.

<img src="/uploads/default/original/2X/6/66964a25543db55b9c9a4efa664d95a653a4bf00.png" width="426" height="186">

Select SSP_License_Example_EvalLicense_....

<img src="/uploads/default/original/2X/0/0cafd5e615262180f675cfe547eec2d45c93110b.png" width="690" height="431">

Click *OK*.

<img src="/uploads/default/original/2X/7/780fad8a60b6593e38a97f6656dd295f46cdf837.png" width="658" height="500">

Close the Welcome Panel.

<img src="/uploads/default/original/2X/d/dc0360d5ee467b5f10192cc6048b655cb66880ef.png" width="398" height="437">

Create a Synergy Configuration perspective. 

<img src="/uploads/default/original/2X/c/c99b1ec21ca6cd6828154910ce133aa10da5eba0.png" width="625" height="474">

In the Synergy Configuration perspective, click on `configuration.xml`, which is in the left panel.

Once it's open, click on **Generate Project Content**

<img src="/uploads/default/original/2X/2/2d0ba37c75436b8856d8d48bfa5a9bbdeeea3795.png" width="690" height="472">

this is the BSP panel

<img src="/uploads/default/original/2X/9/986658e122aa9f2569dadc2aee9d61222fad84dd.png" width="690" height="493">

Build it.

<img src="/uploads/default/original/2X/c/c531daed2f1626aa860b63817611e89e7e98f892.png" width="581" height="500">

When the build is finished, you will get a status message that the build finished with 0 errors and 0 warnings.  During the build, you will see the status window below.

<img src="/uploads/default/original/2X/0/03aa16f78026c23e06b30a691c65f6a6463284ae.png" width="532" height="383">

## Get Compiled .srec

The compiled `.srec` file is in your Debug folder. Use Windows File browser to copy this into the `Put binary here` folder of your S5D9.

<img src="/uploads/default/original/2X/b/bdbbd7513febaafb935cb57b1479d47151aa5ec9.png" width="400" height="500">

These are the files in your development folder on Windows.

<img src="/uploads/default/original/2X/7/721b371785957ad78e1ddc4c62e19f4263e679d6.png" width="643" height="301">

The file is probably in e2_studio -> workspace
<img src="/uploads/default/original/2X/f/fefa2082fc6d4ef09aa043bcf3a809610fa28b54.png" width="678" height="37">

This is the file structure of your S5D9
<img src="/uploads/default/original/2X/f/f7706c5ea7ee97e8d501752998b6d08f61d3500e.png" width="380" height="384">

You need to delete `loaded.txt` and put the name of the binary in a new text file called `update.txt`. See this guide for more information.

http://learn.iotcommunity.io/t/renesas-s5d9-new-binary-install/969