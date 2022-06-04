![Node build](https://github.com/eritislami/evobot/actions/workflows/node.yml/badge.svg)

![logo](https://cdn.discordapp.com/attachments/933698201486237716/947555143795228682/Diseno_sin_titulo_22.png)

# 🤖 Tutorial Discord Bot (TECNO BROS)
> Código del bot del tutorial de TECNO BROS, el vídeo es [este](https://youtu.be/aqMezdz6PlI)
## Requisitos

1. Tener un bot de Discord creado **[Guía](https://www.youtube.com/watch?v=qXev2kf-q_0)**
2. Tener Discord.js V12 o Discord.js V13 **[Guía](https://www.youtube.com/watch?v=qXev2kf-q_0)**
3. Tener el bot hosteado o en tu PC **[Guía](https://www.youtube.com/watch?v=0MkVTtLoMiI)**  
4.1 **(Opcional)** Tener el bot en algun host **[Guía](https://www.youtube.com/watch?v=0MkVTtLoMiI)**

## 🚀 Código de KICK

```js
client.on('message', message => {
    if (!message.guild) return;
  
    if (message.content.startsWith('tb!kick')) {
        const args = message.content.trim().split(/ +/g);
      const user = message.mentions.users.first();
      let razon = args.slice(2).join(" ");
      if(!message.member.hasPermission("KICK_MEMBERS")) return message.channel.send("No tienes permisos para kickear a usuarios");
        if(!razon) return message.channel.send("Pon una razón del baneo");
      if (user) {
        const member = message.guild.members.resolve(user);
        if (member) {
          member
            .kick(razon)
            .then(() => {
              message.channel.send(`@${user.tag} Kickeado con éxito`);
            })
        } else {
          message.channel.send("¡Ese usuario no está en este servidor!");
        }
      } else {
        message.channel.send("No mencionaste al usuario que quieres kickear");
      }
    }
  });
```
## 🚀 Código de BAN

```js
client.on('message', message => {
    if (!message.guild) return;
  
    if (message.content.startsWith('tb!ban')) {
      const args = message.content.trim().split(/ +/g);
      const user = message.mentions.users.first();
      let razon = args.slice(2).join(" ");
      if(!message.member.hasPermission("BAN_MEMBERS")) return message.channel.send("No tienes permisos para banear a usuarios");
      if(!razon) return message.channel.send("Pon una razón del baneo");
      if (user) {
        const member = message.guild.members.resolve(user);
        if (member) {
          member
            .ban({
              reason: razon,
            })
            .then(() => {
              message.channel.send(`@${user.tag} Baneado con éxito `);
            })
        } else {
          message.channel.send("¡Ese usuario no está en este servidor!");
        }
      } else {
        message.channel.send("No mencionaste al usuario que quieres banear");
      }
    }
  });
```
Después de modificar o añadir algo al código, recuerda o reiniciar tu bot o usar el comando `node index.js` para que los cambios se apliquen.

## ⚙️ Uso:

## KICK
![logo](https://cdn.discordapp.com/attachments/933698201486237716/947560035570053200/unknown.png)
![logo](https://cdn.discordapp.com/attachments/933698201486237716/947560638769659915/unknown.png)




## BAN
![logo](https://cdn.discordapp.com/attachments/933698201486237716/947561623982329936/unknown.png)
![logo](https://cdn.discordapp.com/attachments/933698201486237716/947561743876493422/unknown.png)

## 📝 Créditos
* [DISCORD](https://discord.gg/tecnobros)
* [YOUTUBE](https://youtube.com/tecnobros)

Copyright © **1ly4s0#2477** - 2022
