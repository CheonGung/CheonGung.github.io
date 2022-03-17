---
layout: single
title:  "python-discord.py를 이용한 디스코드 봇 만들기 1.기본구조"
categories: discord.py
tags: [Python, discord.py]
---
 discord.py 공식 사이트 주소: <a href="https://discordpy.readthedocs.io/en/stable/" target="_blank">https://discordpy.readthedocs.io/en/stable/</a>
<hr>

 설치할 파이썬 라이브러리
```cmd
pip install discord
pip install asyncio
```
<hr>

 실행을 위한 기본 구조

```python
import discord, asyncio
from discord.ext import commands, tasks

game = discord.Game("!명령어") #봇의 상태를 "!명령어"로 설정(아래 그림 참고)
bot = commands.Bot(command_prefix='!', status=discord.Status.online, activity=game)
#command_prefix: 사용자가 명령을 입력하기 위해 명령어 앞에 사용할 기호 설정
#status: 봇의 상태를 online으로 설정
#activity: 활동 상태를 설정

bot.run("ABCDEFGHIJKLMNOP.ABCDEFG.ABCDEFGHIJKLMNOP")
#bot.run안에 큰따옴표 안에 봇의 토큰값을 넣어준다.

@bot.event
async def on_ready():
    print("봇 시작")
#discord.py에서는 프로그램이 동작할 준비가 되면 on_ready()함수를 발동시킨다.
#동작할 준비가 되었는지 확인을 위해 print("봇 시작")과 같은 코드를 삽입할 수 있다.
```
<hr>
![taulbot1](../../images\taulbot1.PNG)