
# Bot Example - discord.py

This page will provide a basic example of a discord bot built with discord.py with the purpose of using our API.


| Libraries | Install | 
| ----------- | ------------- |
| discord.py    |  `pip install discord.py`|
| aiohttp   |  `comes with dpy`|
| json    |  `default with py`|

=== "Bot"
    ```python
    import discord
    import aiohttp
    import json
    from discord.ext import commands

    ## FYI: This bot is a very basic example on how to use the d.py library with RoServices API. It should not really be used for anything practical. 

    intents = discord.Intents.all() # Setting intents to all for the sake of convenience

    bot_description = '''
    A basic Python Discord bot made to serve as an example on using the RoServices API. 
    '''

    class SampleBot(commands.Bot):
        def __init__(self, *args, **kwargs):
            super().__init__(*args, **kwargs)

        async def on_ready(self):
            print(f'{self.user} is online, on discord.py - {discord.__version__}')
        
        async def setup_hook(self):
            self.session = aiohttp.ClientSession()
        
        async def close(self):
            await self.session.close()


    bot = SampleBot(
        command_prefix="r!", # Change your prefix
        description=bot_description,
        intents=intents,
    )

    groupid = 0 # Put group id
    gamekey = '' # put game key

    async def promoteUser(user):
        body = {'userId': user, 'groupId': groupid}
        headers = {'content-type': 'application/json', 'key': gamekey}

        r = await bot.session.post('https://api.roservices.app/api/ranking/promote', data=json.dumps(body), headers=headers)

        if r.status == 200:
            return "That user has been successfully promoted!"
        else:
            return "Something went wrong!"

    async def setRank(user, rank):
        body = {'userId': user, 'groupId': groupid, 'rank': rank}
        headers = {'content-type': 'application/json', 'key': gamekey}

        r = await bot.session.post('https://api.roservices.app/api/ranking/setrank', data=json.dumps(body), headers=headers)
        print("Status:" + r.status)

        if r.status == 200:
            return "That user has been successfully ranked!"
        else:
            return "Something went wrong!"


    @bot.command()
    async def promote(ctx, user: int):
        promotion = await promoteUser(user)
        await ctx.send(promotion)


    @bot.command()
    async def setrank(ctx, user: int, rank: int):
        ranking = await setRank(user, rank)
        await ctx.send(ranking)


    bot.run('') # Bot Token goes here
    ```

