
class CupMeterBot(loader.Module): """Автоматизирует работу с @CupMeterBot (автоматический майнинг и др.)"""

strings = {"name": "CupMeterBot"}

async def cupmetermd(self, message):

 """Включается команда `/Cup_up`. """
 self.set("cup-up", True)
 while self.get("cup_up"):
 await message.reply("/cup_up")
 await asyncio.sleep(0.1) 
 await utils.answer( 
 message, "Следующая команда будет произведена через 5 минут.", ) 
await asyncio.sleep(300) 