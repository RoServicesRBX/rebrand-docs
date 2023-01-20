
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

    ![alt text](https://cdn.discordapp.com/attachments/600049019800256564/1065453109603729521/1mKlFIicwe.png "This is what it should look like when you open it")

    <span style="color:#9966ff"> **Now, publish the game and turn on HTTP Requests, third party teleports, and studio api (optional)** </span>


    Once you've done that, head over to the Explorer tab and click the little arrow next to **ServerScriptService** and double click the module named **Configuration**.
    
    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065461955961307146/Q4pS6839sl.png)

    **When you open the module, you should see this. Here is where all of the configuration for the App Center is done.**

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065462239450120252/jrmk2CYUPa.png)

    
    ??? Info "Getting group ID + setting variable"
        1. Head to your group on the ROBLOX page. 

        2. Go to the top of your search bar and double click on the numbers.
        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065463266387705866/dSFZrkM7qI.png)
        3. Then, right click and press copy.

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065462857317232670/8EkFPvo6P3.png)


        4. Next, paste that into the **Group** variable.


        *You're now done with that!**
        
    <span style="color:#9966ff"> **Group Variable** </span>:
    - The group Variable is used to define what group this rank center is for. Remove the numbers that are in it and replace it with your group ID. (Click the *Click to see* arrow below)

    <span style="color:#9966ff"> **GameKey Variable** </span>:
    - The game key variable is set the place ID. DO NOT CHANGE THIS.

    <span style="color:#9966ff"> **Lives Variable** </span>:
    - This variable is basically the number of questions a user can get wrong before they fail. By default it is set to 3, but you're able to make it whatever you want. 

    <span style="color:#9966ff"> **PassRank Variable** </span>:
    - This variable is the rank the user will get once they pass the application. 

    <span style="color:#9966ff"> **Amount Variable** </span>:
    - This variable is the amount of question in the application. Be sure that it matches the amount of questions you have inside of the `questions` dictionary. 

---

??? Example "Adding Questions"

    Adding and removing questions is a very basic process. In order to do this, find the questions dictionary, it should look like this:

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065464252690862100/Vf1gSLvnMx.png)

    **By default the application center comes with three pre-made questions. Replace each value with whatever you want for it.**

    - <span style="color:#9966ff"> **Values in the Questions' dictionary** </span>:
        * **Question number**: Put in the question number. 
        * **Question**: Put the question you want the user to answer iside of the quotes.
        * **Answers**: 4 Answer choices are **required**. Replace whatever is in the quotes with the answer you want to put.
        * **Correct answer**: put the number of the correct answer.

    **Adding questions**

    To add a question, copy one of the question dictionaries, and paste it after an };. Then change the question number to the question it is.

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

    ![Gif](https://cdn.discordapp.com/attachments/600049019800256564/1065465695325917244/ssd.gif)

??? Example "Removing Questions"

    To remove questions, its pretty simple. Do the exact same thing as adding a question, except delete the question. 

    ![Gif](https://cdn.discordapp.com/attachments/600049019800256564/1065466566709362718/ss2.gif)
--- 
