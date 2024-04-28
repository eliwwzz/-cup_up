__version__ = (0, 0, 7)
#
#
# _           _            _ _
# | |         | |          (_) |
# | |     ___ | |_ ___  ___ _| | __
# | |    / _ \| __/ _ \/ __| | |/ /
# | |___| (_) | || (_) \__ \ |   <
# \_____/\___/ \__\___/|___/_|_|\_\
#
#              © Copyright 2024
#
# 🔒 Licensed under the GNU AGPLv3
# 🌐 https://www.gnu.org/licenses/agpl-3.0.html

# meta developer: @eliwwzz
# meta banner: https://i.imgur.com/awltLuz.jpeg


from .. import loader, utils
import asyncio


class DrochBotMod(loader.Module):
    """Автоматизирует работу с @CupMeterBot (автоматическая фарма и др.)"""

    strings = {"name": "CupMeter"}

    async def drochcmd(self, message):
        """Включается команда `/cup_up`. Чтобы остановить, `Майнинг стоп`."""
        self.set("main", True)
        while self.get("main"):
            await message.reply("/cup")
            await asyncio.sleep(0.1)
            await utils.answer(
                message,
                "Следующая команда будет произведена через 5 минут.",
            )
            await asyncio.sleep(300)