# Capture Requests From Mobile Using Burp Suite
Require: Install BurpSuite (PROFESSIONAL/COMMUNITY EDITION), Mobile Device connect in the same LAN with PC
## I. IOS physical device:
- Step 1: Configure the BurpSuite Proxy listener
  - Open BurpSuite then click Settings to open the Settings dialog.
  - ![image](https://user-images.githubusercontent.com/58378623/225493773-faee54d3-5ac8-43f6-aa25-ed1dd45e1beb.png)
  - Go to Tools > Proxy.
  - In Proxy listeners, click Add.
  - In the Binding tab, set Bind to port to 8082 (or another port that is not in use).
  - Select All interfaces and click OK.
  - At the prompt, click Yes.
  - ![image](https://user-images.githubusercontent.com/58378623/225494271-d1fff140-3ba6-4b0f-aa4e-aab67b44ac97.png)

 - Step 2: Configure your IOS device to use the proxy
  - In your iOS device, go to Settings > Wi-Fi.
  - Make sure that the Wi-Fi button is on and connect to your Wi-Fi network.
  - Select the information icon (i) next to your Wi-Fi network.
  - ![image](https://user-images.githubusercontent.com/58378623/225494540-ccac32a4-db75-49ea-8616-6204ee9fb13f.png)

  - Set Configure Proxy to Manual.
  - Set Server to the IP address of the computer that is running Burp Suite Professional.
  - Set Port to the port value that you configured for the Burp Proxy listener, in this example 8082
  - Touch Save
  - ![image](https://user-images.githubusercontent.com/58378623/225494582-f811de75-59e6-4096-b6b5-702848159204.png)
- Step 3: Install a CA certificate on your iOS device
  - In order to interact with HTTPS traffic, you need to install a CA certificate from your BurpSuite installation on your iOS device. To install the CA certificate to your iOS device:
  - Make sure that BurpSuite is running on your computer.
  - Use the browser on your iOS device to go to http://burpsuite and select CA Certificate.
  - When the CA certificate downloads, select Profile downloaded in the Settings menu.
  - On the Install Profile screen, select Install.
  - ![image](https://user-images.githubusercontent.com/58378623/225494848-3562941f-745e-4fa5-a207-0df5007dc348.png)
  - On the Installing Profile screen, select Install.
  - When the profile is installed, select Done.
  - Go to Settings > General > About > Certificate Trust Settings.
  - Activate the toggle switch for Portswigger CA.
  - ![image](https://user-images.githubusercontent.com/58378623/225494992-ad4cd909-d2f9-4660-a567-87f1ebf9a9f1.png)
- Step 4: Test the configuration
  - Open BurpSuite.
  - Go to Proxy > Intercept and click Intercept is off to switch intercept on.
  - Open the browser on your iOS device and go to an HTTPS web page.
  - The page should load without any security warnings. You should see the corresponding requests within BurpSuite.
## II. Android physical device.
- Step 1: The same with IOS
- Step 2: Configure your device to use the proxy
  - In your Android device, go to Settings > Network & internet.
  - Select Internet and long-press the name of your Wi-Fi network.
  - Select Modify.
  - From the Advanced options menu, select Proxy > Manual.
  - Set Proxy hostname to the IP of the computer running BurpSuite.
  - Set Proxy port to the port value that you configured for the Burp Proxy listener, in this example 8082.
  - Touch Save.
- Step 3: Install a CA certificate on your Android device
  - In order to interact with HTTPS traffic, you need to install a CA certificate from BurpSuite on your Android device. This step is complicated and it varies across devices and versions of Android.
  - In addition, you need to make further configuration changes in order to proxy HTTPS traffic from a Chrome browser that's at version 99 or above.
  - For further information on how to perform these steps, you can refer to the following external links. Please note that we're not responsible for the content of these pages:
    - https://blog.ropnop.com/configuring-burp-suite-with-android-nougat
    - https://httptoolkit.com/blog/chrome-android-certificate-transparency
- Step 4: Test the configuration
  - Open Burp Suite Professional.
  - Go to Proxy > Intercept and click Intercept is off to switch intercept on.
  - Open the browser on your Android device and go to an HTTPS web page.
  - The page should load without any security warnings. You should see the corresponding requests within Burp Suite Professional.
## III. Android emulator:
- Step 1: 
