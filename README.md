# P-XEL-COMMUNTY
const ppfun = require("ppfun-admin-api")
const config = require("./config.json");

const bot = new ppfun.Bot();

// Notify when connected
bot.addListener("open", () => {
    console.log("Connected to the server!")
})

// Log messages
bot.addListener("chatMessage", (message) => {
    console.log(`${message.getAuthor().getName()}: ${message.getContent()}`)
})

// Connect
bot.connect(
    config.url, 
    config.apiKey, 
    ppfun.Subscriptions.CHAT
)
