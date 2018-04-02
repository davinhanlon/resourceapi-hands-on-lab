# HTTP, it will make your hair curl

## Introduction
Before we start coding / puppetizing we need to see if our light bulbs even work.

## Where are you ??

Go here https://www.meethue.com/api/nupnp This should give you an IP address to connect to.
Then point your web browser at the ip eg http://192.168.0.2/
If you have a developer key for your hub skip to the last section

## Security 

Before you can interact with the hue, you need to generate a developers key for hue, this is typical for most IOT devices, sometimes is is a user/password others a key. Point your browser here http://192.168.0.2/debug/clip.html
Put this in the body
url /api/
body ```{"devicetype":"my_hue_app#<something here>"}```
Press post
Press the button on the hub
press post again
you will now be given a user name
eg 
```
	{
		"success": {
			"username": "jheDoeqKBKnlJuzoDiB5ZxNxJBYsMvzLT3ubMw8n"
		}
	}
```

## I'm bored when can i play with the lights !!!
Using curl and jq, to find out more 
curl http://192.168.0.2/api/jheDoeqKBKnlJuzoDiB5ZxNxJBYsMvzLT3ubMw8n/lights | jq
You will likely have 3 lights in various states
To turn a light off
curl http://192.168.0.2/api/jheDoeqKBKnlJuzoDiB5ZxNxJBYsMvzLT3ubMw8n/lights/3/state  -X PUT -d '{"on":false}'
To turn a light on
curl http://192.168.0.2/api/jheDoeqKBKnlJuzoDiB5ZxNxJBYsMvzLT3ubMw8n/lights/3/state  -X PUT -d '{"on":true}'
