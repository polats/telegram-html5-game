# Telegram HTML 5 Game Extension for Scaffold-ETH 2

## Getting Started

### Prerequisites

* Install [ngrok](https://ngrok.com/)
    *  ```npm install -g ngrok```
    * Set up an ngrok account on [ngrok.com](https://ngrok.com/)
* Install [vercel](https://vercel.com/) cli
    * ```npm install -g vercel```
* Obtain a [Bot Token](https://core.telegram.org/bots/tutorial#getting-ready) from Telegram

### Run Locally

* Create an ngrok tunnel
    * ```ngrok http 3000```
    * retrieve the NGROK_URL from the command line, it should look similar to ```https://dd9b-2607-fea8-85a2-a100-9830-206a-d1d8-9cb1.ngrok-free.app```


* create an ```.env``` file with the bot token and ngrok url
    * **NOTE:** NGROK_URL changes every time the ```ngrok http 3000``` command is run
```
BOT_TOKEN=[retrieved from telegram]
NGROK_URL=[shown on command line]
```

* start the server locally
    * ```vercel dev```

![alt text](images/vercel_dev.png)

* set the telegram webhook for local testing
    * ```yarn set-webhook-local```

* verify webhook is running
    * ```yarn get-webhook-info```

* Test bot by sending a message on telegram

![alt text](images/chat_result.png)

### Deploy on Vercel

* add ```BOT_TOKEN``` environment variable in vercel project settings 
* deploy app on vercel
  * ```vercel --prod```
* retrieve production url from [vercel](https://vercel.com/) and update .env file
```
VERCEL_ENV=[domain assigned by vercel]
```
* update webhook to production
  * ```yarn set-webhook-prod```

* verify webhook is updated to production url
    * ```yarn get-webhook-info```

* Test bot by sending a message on telegram
