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
MTEwNjY0NTE1MTc5Mjc3NTE2OA.G9QZ-U.irCXvSoLttdZwaDS9ybfUwg5kVyQaICAw65GPE
bot.run("YOUR_BOT_TOKEN") pip install discord.py
pip install discord.py
pip install discord-components


