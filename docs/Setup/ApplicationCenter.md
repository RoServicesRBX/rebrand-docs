
## **Application Center Configuration**

The application center is a very customizable and user friendly system which allows a player to do an application, and once passed, it will **automatically** give them a rank you specify! 

??? Info "Prerequisites - Make sure you have these done before continuing"
    [Go to Setup Instructions](/Setup/Dashboard)

    - Bot Account Set up 
    - Place Whitelisted
    - Valid Gamekey

??? Question "How to publish your game"
    
    To publish a game, head on over to the top left corner and hit file. 

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065467105283153930/LF7IXqrXbB.png)

    Then press "Publish to Roblox"

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065467299227775027/hOR18dbNlg.png)
    !!! Success "Congrats"


??? Question "How to turn on required services"

    To turn on required services, make sure the game is published then head over to the game settings tab.

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065467619966201906/HxjDFoI8hl.png)

    Then turn on allow HTTP Requests, Third Party Teleports, and Third Party Sales.

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065468514846130296/rY0KCkreuf.png)
    !!! Success "Services are now on"


## **Template Setup**

??? Abstract "Overview"

    Open the application center template you have downloaded. 

     *What it should look like when you open it:*

    ![alt text](https://cdn.discordapp.com/attachments/600049019800256564/1068972462005551254/w3o31YK6hT.png "This is what it should look like when you open it")

    <span style="color:#9966ff"> **Now, publish the game and turn on HTTP Requests, third party teleports, and studio api (optional)** </span>

    Once you've done that, head over to the Explorer tab and click the little arrow next to **ServerScriptService**, open the **RemoteEvents** folder then and double click the script called **APIHandler**.
    
    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068961783555043439/khjIufIcxM.png)

    **When you open the script, you should see this. This is where all of the basic configuation is done.**

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068971377727651993/aZJz6x5LCJ.png)


    ??? Info "Getting group ID + setting variable"
        1. Head to your group on the ROBLOX page. 

        2. Go to the top of your search bar and double click on the numbers.
        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065463266387705866/dSFZrkM7qI.png)
        3. Then, right click and press copy.

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065462857317232670/8EkFPvo6P3.png)


        4. Next, paste that into the **Group** variable.


        *You're now done with that!**
        
    <span style="color:#9966ff"> **groupID Variable** </span>:
    - The group Variable is used to define what group this rank center is for. Remove the numbers that are in it and replace it with your group ID. (Click the *Click to see* arrow below)

    <span style="color:#9966ff"> **gameKey Variable** </span>:
    - Copy & Paste your gamekey (obtained in the dashboard) into there.

    <span style="color:#9966ff"> **rankID Variable** </span>:
    - This variable is the rank the user will get once they pass the application. 

    <span style="color:#9966ff"> **successMessage Variable** </span>:
    - Set the message you want to say after a user has passed the application.

    **To change how many lives you get in the application, change this INT value located in StarterGui under the Values folder in the screenGUI.**
    
    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068975680685084692/mtZKwFHSx3.png)

    !!! Success "End of APIHandler Setup"
---
## **Question Setup**

??? Abstract "Configuration (Module)"

    To configure the Application questions & some UI elements, head to **ReplicatedStorage**, open the **Modules** folder -> **UI_Settings** -> **Core**

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068965235102322788/AqnxDEFQJ5.png)

    **After opening the Module, you should see something similar to this**

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068965808673390624/dmy2dQyqri.png)

    Start by putting your group name and center name into these fields. If you want **Dark** theme, put "Dark" in the theme value. Otherwise, leave it blank if you're making your own UI.

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068974152293298176/PLNqQSg6nH.png)

    Then Start Configuring the questions.

    Things to remember:

    - Adjust the **Amount Variable** to how many questions you have
    - All Questions **require** 4 answer choices
    - Change the number after "Question" to the question number.

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068967448881156256/3AzwDHi4EE.png)

??? Example "Adding Questions"

    Adding and removing questions is a very basic process. In order to do this, find the questions dictionary, it should look like this:

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068968379966304317/QNKb6C3lxp.png)

    **By default the application center comes with three pre-made questions. Replace each value with whatever you want for it.**

    - <span style="color:#9966ff"> **Values in the Questions' dictionary** </span>:
        * **Question number**: Put in the question number. 
        * **Question**: Put the question you want the user to answer iside of the quotes.
        * **Answers**: 4 Answer choices are **required**. Replace whatever is in the quotes with the answer you want to put.
        * **Correct answer**: put the number of the correct answer.

    **Adding questions**

    To add a question, copy one of the question dictionaries, and paste it after an };. Then change the question number to the question it is. (Remember to change the total number of questions as well!)

    ```lua
    Question1 = {
                Question = "Who is god?";
                Answer1 = "Ava";
                Answer2 = "Billy";
                Answer3 = "Brandon";
                Answer4 = "idk";
                CorrectAnswer = 1;
            };
    ```

    ![Gif](https://cdn.discordapp.com/attachments/600049019800256564/1068968057562742864/appgif.gif)

??? Example "Removing Questions"

    To remove questions, its pretty simple. Do the exact same thing as adding a question, except delete the question. 

    ![Gif](https://cdn.discordapp.com/attachments/600049019800256564/1068968792841003058/app2.gif)
--- 

??? Abstract "UI Configuration"

    Like many others, we believe that the ability to customize things to your personal liking is an absolute. Our Application Centers allow you to adjust or even redesign the template UI. To get started go **StarterGUI** and open up the ScreenGUI. Feel free to do whatever you want.

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1068975083051294871/byezalbyr6.png)
