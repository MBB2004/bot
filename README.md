import discord
from discord.ext import commands

# Botun prefixi
prefix = "$"

# Discord botunun ayarları
intents = discord.Intents.default()
intents.messages = True
bot = commands.Bot(command_prefix=prefix, intents=intents)

# Botun hazır olduğunda çalışacak kod
@bot.event
async def on_ready():
    print(f'{bot.user.name} is ready!')

# Hello komutu
@bot.command()
async def hello(ctx):
    await ctx.send(f'Hi! I am a bot {bot.user.name}!')

# Heh komutu
@bot.command()
async def heh(ctx, count_heh=5):
    await ctx.send("he" * count_heh)

# Bot tokeni
token = "MTIyMzk1ODc3NDczNDEyNzIxNQ.G4FQ8l.I3R3_06ZV70-bfp_FEkg-nPQ2k4_JEBN60E_N0"

# Botu çalıştırma
bot.run("MTIyMzk1ODc3NDczNDEyNzIxNQ.G4FQ8l.I3R3_06ZV70-bfp_FEkg-nPQ2k4_JEBN60E_N0")
