# North Star Support Bot

A simulated customer support chatbot for a small outdoor apparel and camping gear store. It handles order tracking, returns and exchanges, product recommendations, and handoff to a live agent, with fallback handling for anything it doesn't understand.

The whole thing is a single HTML file. There is no build step, no server, no API key, no account, and no internet connection required.

## How to run and test

1. Download `north-star-support-bot.html`.
2. Double-click it (or right-click and open with any modern browser: Chrome, Edge, Firefox, or Safari).
3. Start chatting. You can either type messages or tap the suggested buttons.

That's the entire setup. Nothing else is needed to review it.

## What it does

- **Order tracking** - ask for an order number and return its status.
- **Returns and exchanges** - explains the return policy and gives a returns link.
- **Product recommendations** - asks a couple of clarifying questions, then recommends a product category.
- **Live agent handoff** - transitions to a simulated live agent, and lets you return to the main menu at any time.
- **Fallback** - if a message isn't understood, it says so and offers options or escalation.

## Test data

The bot uses this mock order data:

| Order number | Response |
| --- | --- |
| #111 | Shipped, arriving tomorrow |
| #222 | Processing, ships in 24 hours |
| #333 | Delivered (asks a follow-up) |
| anything else | Invalid order |

Reference information built in:

- Return policy: 30-day returns, items must be unused, original packaging required.
- Shipping: Standard 3-5 business days, Expedited 1-2 business days.

## How to test each feature

Type these (or variations of them) to check each path:

| Try typing | What you should see |
| --- | --- |
| `where's my order?` then `#111` | Asks for an order number, then returns "Shipped, arriving tomorrow" |
| `track my package` then `222` | Same tracking flow, returns "Processing, ships in 24 hours" |
| `333` | "Delivered", then a follow-up question |
| `999` | "Invalid order" message |
| `I need a refund` | Full return policy and returns link |
| `how long is shipping?` | Standard and Expedited shipping times |
| `recommend some gear` then pick answers | Two questions, then a recommended category |
| `talk to a human` | Connects to the simulated live agent, with a "Return to main menu" option |
| `asdfghjkl` | Fallback message with options |

The intent matching handles different phrasings, casing, and minor typos, so "Where is my order", "track my package", and "wheres my stuff" all reach the same flow.

## Requirement checklist

- [x] All four required use cases implemented
- [x] Order tracking uses the provided mock data exactly
- [x] Return policy and shipping information included where relevant
- [x] Intent recognition supports multiple phrasing variations
- [x] Fallback handling implemented
- [x] Users can return to the main menu after the live agent handoff
- [x] Reviewable with no API keys, subscriptions, accounts, or setup steps

## Notes

- The file is fully self-contained and works offline. It makes no network calls when opened.
- The returns link points to a placeholder URL (`northstaroutdoors.com/returns`) for demo purposes. Swap it for a real link if one is provided.
- Use the restart button in the top-right of the chat header to reset the conversation at any time.

## Files

- `north-star-support-bot.html` - the chatbot (open this to run it).
- `README.md` - this file.
