import discord
from discord.ext import commands
from discord_components import DiscordComponents, Button, ButtonStyle

intents = discord.Intents.default()
intents.typing = False
intents.presences = False

bot = commands.Bot(command_prefix="!", intents=intents)
DiscordComponents(bot)

@bot.event
async def on_ready():
    print(f"Bot {bot.user.name} olarak giriş yaptı.")

@bot.command()
async def hello(ctx):
    await ctx.send("Merhaba! Butonlu bir mesaj örneği:", 
                   components=[Button(style=ButtonStyle.blue, label="Tıkla", emoji="✨")])

@bot.event
async def on_button_click(interaction):
    if interaction.component.label == "Tıkla":
        await interaction.respond(content="Butona tıklandı!", ephemeral=True)

e8dedb3a448a2f0d22bdf259b6d93f9666542b2456bc99eb36b75939d3c6b87a
bot.run("YOUR_BOT_TOKEN") pip install discord.py
pip install discord-components

