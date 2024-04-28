__version__ = (0,0,1) 
# meta developer: @eliwwzz @GamesAomame
from .. import loader, utils
import asyncio


class CupMeterBot(loader.Module):
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
