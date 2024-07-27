<!-- # Bug Reports -->
> **Note:** Mobile bugs for the City&Me application are temporarily displayed here until the bugs for the Benefiti.rs website are approved for public viewing.

**BUGS:
During the mobile testing process, the production version of the City & Me application was used. Below are detailed examples of bugs identified and documented:**

**Bug** **1:**

**Title:** Application does not indicate loss of Wi-Fi connection during
use of internet-dependent features

**Description:** When the internet connection (Wi-Fi) is disabled while
using the application, there is no indication within the app that the
connection has been lost. This issue can lead to confusion as the app
continues to appear connected, but fails to load new data or perform
actions requiring internet access.

**Environment:** Real Device, Mobile, Android 14, Galaxy A53 5G

**Precondition:** The user has an active Wi-Fi connection when starting
the application. The store has shopping items.

**Steps** **to** **Reproduce:**

> 1\. Launch the application,
>
> 2\. Disable the Wi-Fi connection on the device,
>
> 3\. Click on “Moj novčanik”,
>
> 4\. Click on “Prodavnica”.

**Expected** **Results:** The application should display an alert or
indication that the internet connection has been lost, prompting the
user to check their connection.

**Actual** **Results:** The screen “Prodavnica” is empty (doesn’t show
any items).

**Severity:** Low

**Priority:** Medium

**Attachment:**
[empty-store-when-no-wifi.mp4](https://drive.google.com/file/d/1CULarPkXgBFttGxQ7r6KfM8iAycwVxN3/view?usp=drive_link)

**Bug** **2:**

**Title:** Store items remain displayed when WiFi is disconnected

**Description:** When the Wi-Fi connection is disabled while the user is
on the "Prodavnica" screen, the items continue to be displayed. Even
after manually refreshing the screen or

minimizing and reopening the app, the store items do not update to
reflect the current connection status.

**Environment:** Real Device, Mobile, Android 14, Galaxy A53 5G

**Precondition:** The user is logged in. The user has an active Wi-Fi
connection when starting the application. The store has shopping items.

**Steps** **to** **Reproduce:**

> 1\. Click on “Moj novčanik”,
>
> 2\. Click on “Prodavnica”,
>
> 3\. Disable the Wi-Fi connection on the device,
>
> 4\. Manually refresh the "Store" screen,
>
> 5\. Minimize the app and reopen it.

**Expected** **Results:** The application should detect the loss of
Wi-Fi connection and indicate that the connection is lost.

**Actual** **Results:** The store items remain displayed after the Wi-Fi
connection is disabled. Manual refresh and minimizing/reopening the app
do not update the items to reflect the current connection status.

**Severity:** Low

**Priority:** Medium

**Attachment:**
[store-items-stay-displayed-when-no-wifi.mp4](https://drive.google.com/file/d/1Ce-HKeXJYE3VSZ-nrNZN4XxxTex6M7HB/view?usp=drive_link)

**Bug** **3:**

**Title:** Layout does not adjust to screen size after rotating from
landscape to portrait mode

**Description:** When the application is opened in landscape mode and
then rotated to portrait mode, the layout does not adjust to the screen
size. Elements appear cut off, affecting the usability of the
application.

**Environment:** Real Device, Mobile, Android 14, Galaxy A53 5G

**Precondition:** The user is logged in. Autorotate is on.

**Steps** **to** **Reproduce:**

> 1\. Open the application in landscape mode,
>
> 2\. Rotate the device to portrait mode.

**Expected** **Results**: The layout should dynamically adjust to the
new screen size after rotation, maintaining proper alignment and
visibility of all elements.

**Actual** **Results:** The layout fails to adjust to the new screen
size after rotating from landscape to portrait mode. Elements appear cut
off.

**Severity:** Low

**Priority:** Medium

**Attachment:**
[layout-from-landscape-to-portrait.mp4](https://drive.google.com/file/d/1Dntyz8_4Qm1y3_CUs5ZiWp-moKpz7eaB/view?usp=drive_link)

