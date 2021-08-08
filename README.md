- 👋 Hi, I’m @dev22334
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
dev22334/dev22334 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
const { Client, Collection } = require("discord.js");
const { config } = require("dotenv");
const {prefix, token } = require("./config.json")
const { CanvasSenpai } = require("canvas-senpai")
const canva = new CanvasSenpai();
const db = require("quick.db"); 

const discord = require("discord.js");
const client = new discord.Client({

  disableEveryone: false
});

require('discord-buttons')(client)
// go to package to update some stuff
client.commands = new Collection();
client.aliases = new Collection();


// Run the command loader
["command"].forEach(handler => {
    require(`./handlers/${handler}`)(client);
});

client.on("ready", () => {
    console.log(`Hi, ${client.user.username} is now online!`);

    client.user.setPresence("I am Devil") 
})

client.on("message", async message => {
const Aoijs = require("aoi.js")

    if (message.author.bot) return;
    if (!message.guild) return;
    if (!message.content.startsWith(prefix)) return;
const bot = new Aoijs.Bot({
fetchInvites: true,
token: "top secret bot token", //Discord Bot Token
prefix: "prefix", //Customizable
fetchInvites: true
})
bot.onMessage() //Allows to run Commands

    // If message.member is uncached, cache it.
    if (!message.member) message.member = await message.guild.fetchMember(message);
bot.command({
name: "ping",
code: `$ping Pong!` 
})

    const args = message.content.slice(prefix.length).trim().split(/ +/g);
    const cmd = args.shift().toLowerCase();
bot.status({
  text: "coding with the quizzer",
  type: "COMPETING",
  time: 10
})

    if (cmd.length === 0) return;
bot.command({
name: "command name", //Trigger name (command name)
code: `
$title[embed title]
$description[
    // Get the command
    let command = client.commands.get(cmd);
    // If none is found, try to find it by alias
    if (!command) command = client.commands.get(client.aliases.get(cmd));
I like coding discord bots yay lets gooooooo
    // If a command is finally found, run the command
    if (command) 
        command.run(client, message, args);
});
client.login('YOUR TOP SECRET BOT TOKEN HERE');
]
$footer[footer]
$color[RANDOM]
`
}); //Code
