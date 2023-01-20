
## **Rank Center Configuration**

The Rank Center is a template that allows clients to sell ranks as gamepasses. With this product, customers can automatically get roled and the client won't need to worry about confirming if said user truly has bought the rank!


??? Info "Prerequisites - Make sure you have these done before continuing"
    [Go to Setup Instructions](/Setup/Dashboard)

    - Bot Account Set up 
    - Place Whitelisted
    - Valid Gamekey

??? Question "How to publish your game"
    
    To publish a game, head on over to the top left corner and hit file. 

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065469025339064330/u6QdQlxZgA.png)

    Then press "Publish to Roblox"

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065467299227775027/hOR18dbNlg.png)
    !!! Success "Congrats"


??? Question "How to turn on required services"

    To turn on required services, make sure the game is published then head over to the game settings tab.

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065467619966201906/HxjDFoI8hl.png)

    Then turn on allow HTTP Requests, Third Party Teleports, and Third Party Sales.

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065468514846130296/rY0KCkreuf.png)
    !!! Success "Services are now on"


### **Template Setup**

??? Abstract "Overview & Variable Setup"

    After downloading the template, please open it in Roblox Studio.
    What it should look like when you open it:

    ![alt text](https://cdn.discordapp.com/attachments/600049019800256564/1065774911131500645/lgv9mvGeVi.png "This is what it should look like when you open it")


    Once you've done that, head over to the Explorer tab and open **ServerScriptService**. Then, double click the module named **Configuration** to open it. 
    
    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065775278057599006/mRFnyb3FCb.png)

    **After opening the module, you should be greeted with some code that look like this. Here is where all of the configuration is done.**

    ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065775707688554567/5F7XaO5cQt.png)


    **Now, let's talk about what each of these variables do and what the dictionary is used for.**
    

  
    ??? Info "Getting group ID + setting variable"
        1. Head to your group on the ROBLOX page. 

        2. Go to the top of your search bar and double click on the numbers.
        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065463266387705866/dSFZrkM7qI.png)
        3. Then, right click and press copy.

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065462857317232670/8EkFPvo6P3.png)


        4. Next, paste that into the **Group** variable.


        *You're now done with that!**
        
    - **Variables**

        - <span style="color:#9966ff"> **Group Variable** </span>:
        The group variable is used to define what group this rank center is for. Remove the numbers that are in it and replace it with your group ID. 
        
        - <span style="color:#9966ff"> **GameKey Variable** </span>:
        The `GameKey` variable is set the place ID. DO NOT CHANGE THIS. 

        - <span style="color:#9966ff"> **OneTimeRedemption Variable** </span>:
        This variable if set to *true*, it will make it so the person who is claiming the rank can only redeem it once. This means that if the person claims a rank, they will not be able to claim that specific rank again. 

    


??? Info "Dictionary Configuration"

    This dictionary contains three values which are essential for the rank center to function as intended. The Rank ID value, Rank Name value, and the GamePass value. Please see below on how you configure this.

    ??? Example "Configuring Rank ID"

        Head to **your** group on the ROBLOX page. 

        Go to the top right, press the three dots, then click "configure group".
        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065783621337747526/vftrqwwVo2.png)

        Press roles then copy the number of the rank you want to sell.

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065784073685049445/copy.gif)

        Go back to studio then replace the RankID variable with that number.

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065785598234853426/rankid.gif)


    ??? Example "Configuring Rank Name"
        Next replace the text in "Rank Name" with the name of the role associated with the ID.

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065786420184240159/rankname.gif)

    
    ??? Example "Configuring Gamepass ID"
        Go to the gamepass on Roblox then copy the the ID.

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065787679297507428/pass.gif)

        Afterwards, replace the current numbers in `GamePass` with your id.
        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065787941466677339/gamepass.gif)

    !!! Success "Now you're done with the studio set up!"
    --- 

    ??? Example "Adding Ranks"
        **To add more ranks**:
        Copy this below and paste it after each };
        ```lua
        {
        RankID = 0; -- Change to the Rank ID
        RankName = ""; -- Put the name of the Rank
        isFree = false; --<= if you want the rank to be free set it to true and set GamePass to 0 or nil.
        GamePass = 0; -- set the gamepass ID
        }; 
        ```

        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065788740439638146/adding.gif)

    ??? Example "Removing Ranks"

        I removed three ranks here, if you only want to remove one, do as I did but only select one.
        ![alt](https://cdn.discordapp.com/attachments/600049019800256564/1065788311337189458/remove.gif)
      