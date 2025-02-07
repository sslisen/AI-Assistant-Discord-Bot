# ChatGPT Discord Bot

> ### Build your own Discord bot using ChatGPT
>
---
> **Warning**
>
> #### 2023-04-12 Bing now supported
> #### 2023-04-01 Only Plus account can access Unofficial model
> #### 2023-03-27 Bard now supported

## Features

* `/chat [message]` Chat with ChatGPT!
* `/draw [prompt]` Generate an image with the Dalle2 model
* `/switchpersona [persona]` Switch between optional chatGPT jailbreaks
   * `random`: Picks a random persona
   * `chatGPT`: Standard chatGPT mode
   * `dan`: Dan Mode 11.0, infamous Do Anything Now Mode
   * `sda`: Superior DAN has even more freedom in DAN Mode
   * `confidant`: Evil Confidant, evil trusted confidant
   * `based`: BasedGPT v2, sexy gpt
   * `oppo`: OPPO says exact opposite of what chatGPT would say
   * `dev`: Developer Mode, v2 Developer mode enabled

* `/private` ChatGPT switch to private mode
* `/public` ChatGPT switch to public mode
* `/replyall` ChatGPT switch between replyAll mode and default mode
* `/reset` Clear ChatGPT conversation history
* `/chat-model` Switch different chat model
   * `OFFICIAL-GPT-3.5`: GPT-3.5 model
   * `OFFICIAL-GPT-4.0`: GPT-4.0 model (make sure your account can access gpt-4 model)
   * `Website ChatGPT-3.5`: Website ChatGPT-3.5 model (UNOFFICIAL)
   * `Website ChatGPT-4.0`: Website ChatGPT-4.0 model (UNOFFICIAL)(available if you got a plus account)
   * `Bard`: Google Bard Model

### Chat

![image](https://user-images.githubusercontent.com/89479282/206497774-47d960cd-1aeb-4fba-9af5-1f9d6ff41f00.gif)

### Draw

![image](https://user-images.githubusercontent.com/91911303/223772051-13f840d5-99ef-4762-98d2-d15ce23cbbd5.png)

### Switch Persona

> **Warning**
>
> Using certain personas may generate vulgar or disturbing content. Use at your own risk.

![image](https://user-images.githubusercontent.com/91911303/223772334-7aece61f-ead7-4119-bcd4-7274979c4702.png)



### Mode

* `public mode (default)`  the bot directly reply on the channel

  ![image](https://user-images.githubusercontent.com/89479282/206565977-d7c5d405-fdb4-4202-bbdd-715b7c8e8415.gif)

* `private mode` the bot's reply can only be seen by the person who used the command

  ![image](https://user-images.githubusercontent.com/89479282/206565873-b181e600-e793-4a94-a978-47f806b986da.gif)

* `replyall mode` the bot will reply to all messages in the channel without using slash commands (`/chat` will also be unavailable)

   > **Warning**
   > The bot will easily be triggered in `replyall` mode, which could cause program failures

# Setup

## Critical prerequisites to install

* run ```pip3 install -r requirements.txt```

* **Rename the file `.env.dev` to `.env`**

* Recommended python version `3.9` +
## Step 1: Create a Discord bot

1. Go to https://discord.com/developers/applications create an application
2. Build a Discord bot under the application
3. Get the token from bot setting
   
   ![image](https://user-images.githubusercontent.com/59131974/234871730-9911d4b3-69b5-4f5c-bb6b-ee7e186d3350.png)

4. Store the token to `.env` under the `DISCORD_BOT_TOKEN`
   
   ![image](https://user-images.githubusercontent.com/59131974/234871853-f179c530-8251-4d40-946d-e9cd582ee1e4.png)

5. Turn MESSAGE CONTENT INTENT `ON`

   ![image](https://user-images.githubusercontent.com/89479282/205949323-4354bd7d-9bb9-4f4b-a87e-deb9933a89b5.png)

6. Invite your bot to your server via OAuth2 URL Generator, Open the invitation link in browser to add Bot to your server

   ![image](https://user-images.githubusercontent.com/59131974/234872073-2145d153-a39c-441b-8eb9-9e7b3737416c.png)
## Step 2: Official API authentication

### Geanerate an OpenAI API key
1. Go to https://platform.openai.com/account/api-keys

2. Click Create new secret key

   ![image](https://user-images.githubusercontent.com/59131974/234870877-a982c729-ccb8-4d9f-bc25-602020ee2b4c.png)

3. Store the SECRET KEY to `.env` under the `OPENAI_API_KEY`

4. You're all set for [Step 3](#step-3-run-the-bot-on-the-desktop)

## Step 2: Website ChatGPT authentication - 2 approaches

* 2023-04-01: Only Support Plus Account now

### Email/Password authentication (Not supported for Google/Microsoft accounts)

1. Create an account on https://chat.openai.com/chat and open it

2.  Open console with `F12`
3.  Open `Application` tab > Cookies

   ![image](https://user-images.githubusercontent.com/89479282/229298001-41ab4f61-5b79-4c65-b08c-708ee6fe2304.png)

4. Copy the value for `_puid` from cookies and paste it into `.env` under `PUID`

5. Save your email into `.env` under `OPENAI_EMAIL`

6. Save your password into `.env` under `OPENAI_PASSWORD`

7. You're all set for [Step 3](#step-3-run-the-bot-on-the-desktop)

### ACCESS token authentication
1. Open https://chat.openai.com/api/auth/session

2. Open console with `F12`

3. Open `Application` tab > Cookies

   ![image](https://user-images.githubusercontent.com/89479282/229298001-41ab4f61-5b79-4c65-b08c-708ee6fe2304.png)

4. Copy the value for `_puid` from cookies and paste it into `.env` under `PUID`


5. Copy the value for `accessToken` from cookies and paste it into `.env` under `ACCESS_TOKEN`

6. You're all set for [Step 3](#step-3-run-the-bot-on-the-desktop)

## Step 2: Google Bard authentication
1. Go to https://bard.google.com/

2. Open console with `F12`

3. Open `Application` tab > Cookies

4. Copy the value for `__Secure-1PSID` from cookies and paste it into `.env` under `BARD_SESSION_ID`

5. You're all set for [Step 3](#step-3-run-the-bot-on-the-desktop)


## Step 2: Microsoft Bing authentication
1. **Rename the file `cookies.dev.json` to `cookies.json`**

2. Go to https://bing.com/chat and log in your Microsoft account

3. Use Cookie Editor or similar extensions to export the cookies

3. Paste it into `cookies.json`

5. You're all set for [Step 3](#step-3-run-the-bot-on-the-desktop)

## Step 3: Run the bot on the desktop

1. Open a terminal or command prompt

2. Navigate to the directory where you installed the ChatGPT Discord bot

3. Run `python3 main.py` or `python main.py` to start the bot

## Step 3: Run the bot with Docker

1. Build the Docker image & Run the Docker container `docker compose up -d`

2. Inspect whether the bot works well `docker logs -t chatgpt-discord-bot`

   ### Stop the bot:

   * `docker ps` to see the list of running services
   * `docker stop <BOT CONTAINER ID>` to stop the running bot

### Have a good chat!
## Optional: Disable logging

* Set the value of `LOGGING` in the `.env` to False
## Optional: Setup system prompt

* A system prompt would be invoked when the bot is first started or reset
* You can set it up by modifying the content in `system_prompt.txt`
* All the text in the file will be fired as a prompt to the bot
* Get the first message from ChatGPT in your discord channel!

   1. Right-click the channel you want to recieve the message, `Copy  ID`

        ![channel-id](https://user-images.githubusercontent.com/89479282/207697217-e03357b3-3b3d-44d0-b880-163217ed4a49.PNG)

   2. paste it into `.env` under `DISCORD_CHANNEL_ID`

 ---
 [**中文說明**](https://zero6992.github.io/2023/03/09/chatGPT-discord-bot-chinese/)

