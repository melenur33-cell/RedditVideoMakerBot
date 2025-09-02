from gtts import gTTS
from moviepy.editor import *
import os

# የሴት ድምፅ ስክሪፕት
text = """
ጤና ይስጥልኝ… 
በአጭር ጊዜ ህይወታችሁን ለመቀየር… 
እኛን ያማክሩን ፕሮፋይል ላይ ባለው ስልክ ይደውሉልን!
"""

# ድምፅ ፋይል መፍጠር
tts = gTTS(text=text, lang="am")
tts.save("video_voice.mp3")

# የድምፁን ርዝመት ማወቅ
audio = AudioFileClip("video_voice.mp3")
duration = audio.duration  # የቪዲዮ ርዝመት

# ቀለም ያለው ቢጫ background ቪዲዮ
clip = ColorClip(size=(720, 1280), color=(255, 255, 255), duration=duration)

# የታይሰር ጽሑፎች
txt_clip1 = TextClip("ጤና ይስጥልኝ", fontsize=70, color='black', font="Noto-Sans-Ethiopic-Bold")\
    .set_position("center").set_duration(3)

txt_clip2 = TextClip("በአጭር ጊዜ ህይወታችሁን ለመቀየር", fontsize=60, color='red', font="Noto-Sans-Ethiopic-Bold")\
    .set_position("center").set_start(3).set_duration(5)

txt_clip3 = TextClip("ፕሮፋይል ላይ ባለው ስልክ ይደውሉልን!", fontsize=65, color='blue', font="Noto-Sans-Ethiopic-Bold")\
    .set_position("center").set_start(8).set_duration(duration-8)

# በአንድ ላይ ማዋሃድ
final = CompositeVideoClip([clip, txt_clip1, txt_clip2, txt_clip3])

# ድምፅ ማክረብ
final = final.set_audio(audio)

# ቪዲዮ መቀመጥ
final.write_videofile("final_video.mp4", fps=24)

print("✅ ቪዲዮው ተጠናቀቀ። 'final_video.mp4' እንደተቀመጠ ይመለከቱ።")![1000058246](https://github.com/user-attachments/assets/f9bfc674-6ed4-4b89-93a3-936b8c756bca)

**EXPERIMENTAL!!!!**

On macOS and Linux (debian, arch, fedora and centos, and based on those), you can run an install script that will automatically install steps 1 to 3. (requires bash)

`bash <(curl -sL https://raw.githubusercontent.com/elebumm/RedditVideoMakerBot/master/install.sh)`

This can also be used to update the installation

4. Run `python main.py`
5. Visit [the Reddit Apps page.](https://www.reddit.com/prefs/apps), and set up an app that is a "script". Paste any URL in redirect URL. Ex:`https://jasoncameron.dev`
6. The bot will ask you to fill in your details to connect to the Reddit API, and configure the bot to your liking
7. Enjoy 😎
8. If you need to reconfigure the bot, simply open the `config.toml` file and delete the lines that need to be changed. On the next run of the bot, it will help you reconfigure those options.

(Note if you got an error installing or running the bot try first rerunning the command with a three after the name e.g. python3 or pip3)

If you want to read more detailed guide about the bot, please refer to the [documentation](https://reddit-video-maker-bot.netlify.app/)

## Video

https://user-images.githubusercontent.com/66544866/173453972-6526e4e6-c6ef-41c5-ab40-5d275e724e7c.mp4

## Contributing & Ways to improve 📈

In its current state, this bot does exactly what it needs to do. However, improvements can always be made!

I have tried to simplify the code so anyone can read it and start contributing at any skill level. Don't be shy :) contribute!

- [ ] Creating better documentation and adding a command line interface.
- [x] Allowing the user to choose background music for their videos.
- [x] Allowing users to choose a reddit thread instead of being randomized.
- [x] Allowing users to choose a background that is picked instead of the Minecraft one.
- [x] Allowing users to choose between any subreddit.
- [x] Allowing users to change voice.
- [x] Checks if a video has already been created
- [x] Light and Dark modes
- [x] NSFW post filter

Please read our [contributing guidelines](CONTRIBUTING.md) for more detailed information.

### For any questions or support join the [Discord](https://discord.gg/qfQSx45xCV) server

## Developers and maintainers.

Elebumm (Lewis#6305) - https://github.com/elebumm (Founder)

Jason Cameron - https://github.com/JasonLovesDoggo (Maintainer)

Simon (OpenSourceSimon) - https://github.com/OpenSourceSimon

CallumIO (c.#6837) - https://github.com/CallumIO

Verq (Verq#2338) - https://github.com/CordlessCoder

LukaHietala (Pix.#0001) - https://github.com/LukaHietala

Freebiell (Freebie#3263) - https://github.com/FreebieII

Aman Raza (electro199#8130) - https://github.com/electro199

Cyteon (cyteon) - https://github.com/cyteon


## LICENSE
[Roboto Fonts](https://fonts.google.com/specimen/Roboto/about) are licensed under [Apache License V2](https://www.apache.org/licenses/LICENSE-2.0)
