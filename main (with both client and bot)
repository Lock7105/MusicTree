import os
import discord
import discord.file
from discord.ext import commands
from discord.ext.commands import Bot
from googlesearch import search
import time
import asyncio

bot: Bot = Bot(command_prefix='9')
bot.sniped_messages = {}

for filename in os.listdir('./cogs'):
    if not filename.endswith('.py'):
        continue
    bot.load_extension(f'cogs.{filename[:-3]}')
    print(f'LOADED {filename}')


@bot.event
async def on_ready():
    print('MUSICTREE IS LIVE')


messages = joined = 0


def read_token():
    with open("token.txt", "r") as f:
        lines = f.readlines()
        return lines[0].strip()


token = read_token()

client = discord.Client()


async def update_stats():
    await client.wait_until_ready()
    global messages, joined

    while not client.is_closed():
        try:
            with open("stats.txt", "a") as f:
                f.write(f"Time: {int(time.time())}, Messages: {messages}, Members Joined: {joined}\n")

            messages = 0
            joined = 0

            await asyncio.sleep(5)
        except Exception as e:
            print(e)
            await asyncio.sleep(5)


@client.event
async def on_member_join(member):
    global joined
    joined += 1
    for channel in member.server.channels:
        if str(channel) == "general":
            await client.send_message(f"""Welcome to the server {member.mention}""")


@client.event
async def on_message(message):
    global messages
    messages += 1

    id = client.get_guild('1008870668034641931')
    channels = ["commands"]
    valid_users = ["Ti#9298"]

    if str(message.channel) in channels and str(message.author) in valid_users:
        if message.content.find("!hello") != -1:
            await message.channel.send("Hi")
        elif message.content == "!users":
            await message.channel.send(f"""# of Members: {id.member_count}""")


@bot.event
async def on_message_delete(message):
    bot.sniped_messages[message.guild.id] = (message.content, message.author, message.channel.name, message.created_at)


@bot.command(aliases=['bu'])
@commands.bot_has_permissions(embed_links=True)
async def botupdate(ctx):
    await ctx.send("@everyone", embed=na)


na = discord.Embed(title='Bot Update!', description='Bot Update v2.2')
na.set_footer(text="Bot Update")
na.set_image(url='https://cdn.discordapp.com/attachments/1008874552924839936/1051016058775019610/cigarettes.jpg')
na.set_author(name="trxnity")
na.add_field(name='BOT UPDATE! beats got compressed and now can be uploaded to the server',
             value='[DLINK 1 UPDATE](https://drive.google.com/drive/u/1/folders/1r-HIaqCOjCIeqCBfP_h0bfeQEDbC-Lx8)')


@bot.command()
@commands.bot_has_permissions(embed_links=True)
async def jw999(ctx):
    """
    Juice WRLD Socials
    """
    await ctx.send(embed=jw)


jw = discord.Embed(title="Juice WRLD", description="999", colour=discord.Colour.dark_theme())
jw.set_footer(
    text="Dlink 1 has finally been updated!")
jw.set_image(
    url='https://cdn.discordapp.com/attachments/1008874552924839936/1011068200038957116/artworks-HzToF2q2bszhxhOm-01dMzw-t500x500.jpg')
jw.set_author(name="Juice WRLD",
              icon_url='https://cdn.discordapp.com/attachments/1008874552924839936/1011067927199481906/999.png')
jw.add_field(name="Soundcloud", value='[SoundCloud](https://soundcloud.com/uiceheidd)', inline=False)
jw.add_field(name="Spotify",
             value='[Spotify](https://open.spotify.com/artist/4MCBfE4596Uoi2O4DtmEMz?si=3d0f8af76d044668)',
             inline=True)
jw.add_field(name="Dlink",
             value='[Drive](https://drive.google.com/drive/u/1/folders/12nZrEbaQB3aiUNwHmyLbqImjymEtaMPf)',
             inline=False)
jw.add_field(name="MLeaks", value='[MEGA](https://mega.nz/folder/kjwERKhQ#fSkLabK9qbOOXSwCwJGIaQ)', inline=True)
jw.add_field(name="Instagram", value='[Instagram](https://www.instagram.com/juicewrld999/)', inline=False)
jw.add_field(name='Dlink 2',
             value='[Alternative Link Here!](https://drive.google.com/drive/folders/1-9WGlkzVtI1vdwrQyeoPixxBkWO2tgli?usp=sharing)',
             inline=True)
jw.add_field(name='Merchandise', value='[999club](https://999club.com/)', inline=False)
jw.add_field(name='Documentary',
             value='[HBO MAX DOCUMENTARY](https://drive.google.com/file/d/1uX_aVppgRbgND_2i4d6zk9_Oi0vcSDWn/view?usp=sharing)',
             inline=True)


@bot.command(aliases=['l'])
@commands.bot_has_permissions(attach_files=True)
async def leak(ctx, *, name):
    """
    Get any leak
    """
    embed = discord.Embed(description="Here's Your Leak!")
    embed.set_author(name=f"Juice WRLD",
                     icon_url='https://cdn.discordapp.com/attachments/1008874552924839936/1011067927199481906/999.png')
    embed.add_field(name=f'@{ctx.author.name}! You Typed {name} and these are your results!',
                    value="[Use 9jw999 For More!](https://drive.google.com/drive/u/1/folders/12nZrEbaQB3aiUNwHmyLbqImjymEtaMPf)")
    name = name.lower()
    async with ctx.typing():
        for file in os.listdir(fr"I:\Juice WRLD\JW - Leaks"):
            if name in str(file.lower()):
                await ctx.send(embed=embed, files=[discord.File(fr"I:\Juice WRLD\JW - Leaks\{file}")])


@bot.command()
@commands.bot_has_permissions(attach_files=True)
async def og(ctx, *, name):
    """
    Get any leak
    """
    embed = discord.Embed(description="Here's Your OG File!")
    embed.set_author(name=f"Artist: Juice WRLD",
                     icon_url='https://cdn.discordapp.com/attachments/1008874552924839936/1011067927199481906/999.png')
    embed.add_field(name=f'{ctx.author.name}! You Typed {name} and these are your results!',
                    value="[Use 9jw999 For More!](https://drive.google.com/drive/u/1/folders/12nZrEbaQB3aiUNwHmyLbqImjymEtaMPf)")
    name = name.lower()
    async with ctx.typing():
        for file in os.listdir(fr"I:\Juice WRLD\JW - Leaks\OG Files"):
            if name in str(file.lower()):
                await ctx.send(embed=embed, files=[discord.File(fr"I:\Juice WRLD\JW - Leaks\OG Files\{file}")])


@bot.command(aliases=['s'])
@commands.bot_has_guild_permissions(embed_links=True)
async def snipe(ctx):
    """
Snipes The Last Message
    """
    try:
        contents, author, channel_name, time = bot.sniped_messages[ctx.guild.id]

    except:
        no = discord.Embed(description="***There's Nothing To Snipe!***", color=discord.Color.red())
        await ctx.channel.send(embed=no)
        return

    embed = discord.Embed(description=contents, color=discord.Color.dark_blue(), timestamp=time)
    embed.set_author(name=f"{author}", icon_url=author.avatar_url)
    embed.set_footer(text=f"Sniped in: #{channel_name}")

    await ctx.channel.send(embed=embed)


@bot.command()
@commands.bot_has_guild_permissions(embed_links=True)
async def find(ctx, *, query):
    '''
To search anything on the internet
    '''
    author = ctx.author.mention
    await ctx.channel.send(f"{author} !")
    async with ctx.typing():
        for j in search(query, tld="co.in", num=5, stop=5, pause=2):
            await ctx.send(f"\n:point_right: {j}")
        await ctx.send("Let Me Know What To Find Next!:raised_hands:")


@bot.command(aliases=['snip'])
@commands.bot_has_guild_permissions(attach_files=True)
async def snippet(ctx, *, name):
    """
This Only Works with un-leaked songs
    """
    embed = discord.Embed(description="File Type: Snippet")
    embed.set_author(name=f"Juice WRLD#0999",
                     icon_url='https://cdn.discordapp.com/attachments/1008874552924839936/1011067927199481906/999.png')
    embed.add_field(name=f'You Searched For "{name}" and these are the results!',
                    value="If no snippets are found contact trxnity#0541 or If you're trying to find \n a leaked song there will be no more snippets of that song but u will have the song")
    name = name.lower()
    async with ctx.typing():
        for file in os.listdir(fr"I:\Vids\New Snippets"):
            if name in str(file.lower()):
                await ctx.send(files=[discord.File(fr"I:\Vids\New Snippets\{file}")])
    await ctx.send(embed=embed)


@bot.command(aliases=['c'])
@commands.bot_has_permissions(manage_messages=True)
async def clear(ctx, amount=100):
    if ctx.author.name == 'trxnity':
        await ctx.channel.purge(limit=1)
        await ctx.channel.purge(limit=amount)
        em = discord.Embed(description=f"Successfully cleared {amount} messages", color=discord.Colour.green())
        await ctx.send(embed=em, delete_after=3)
    else:
        em = discord.Embed(title="Missing Perms",
                           description=f"{ctx.author.name} The bot does not have the required ***Manage Messages*** Permissions to use this command",
                           color=discord.Colour.red())
        await ctx.send(embed=em, delete_after=9)


@bot.command(aliases=['r'])
@commands.bot_has_guild_permissions(attach_files=True)
async def released(ctx, *, name):
    embed = discord.Embed(description="Here's Your Song!")
    embed.set_author(name=f"Juice WRLD",
                     icon_url='https://cdn.discordapp.com/attachments/1008874552924839936/1011067927199481906/999.png')
    embed.add_field(name=f'{ctx.author.name}! You Typed {name} and these are your results!',
                    value="[Use 9jw999 For More!](https://drive.google.com/drive/u/1/folders/12nZrEbaQB3aiUNwHmyLbqImjymEtaMPf)")
    name = name.lower()
    async with ctx.typing():
        for file in os.listdir(fr"I:\Juice WRLD\JW - Albums\FOR BOT ONLY (Released)"):
            if name in str(file.lower()):
                await ctx.send(embed=embed,
                               files=[discord.File(fr"I:\Juice WRLD\JW - Albums\FOR BOT ONLY (Released)\{file}")])


@bot.command()
@commands.bot_has_guild_permissions(attach_files=True)
async def beats(ctx, *, name):
    embed = discord.Embed(description="Here's Your Beat!")
    embed.set_author(name=f"Juice WRLD",
                     icon_url='https://cdn.discordapp.com/attachments/1008874552924839936/1011067927199481906/999.png')
    embed.add_field(name=f'{ctx.author.name}! You Typed {name} and these are your results!',
                    value="[Use 9jw999 For More!](https://drive.google.com/drive/u/1/folders/12nZrEbaQB3aiUNwHmyLbqImjymEtaMPf)")
    name = name.lower()
    async with ctx.typing():
        for file in os.listdir(fr"I:\Juice WRLD\JW BEATS\compressed"):
            if name in str(file.lower()):
                await ctx.send(embed=embed,
                               files=[discord.File(fr"I:\Juice WRLD\JW BEATS\compressed\{file}")])


bot.run(token, reconnect=True)
