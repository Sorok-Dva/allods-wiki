Acquaintance with servers
===
The Allods Environment has two spaces: base and shard parts.

Base part
---
The Base part is most important group of servers which should be started first. Allods Environment has only one base part which has following servers :

- Account Server is server that authenticates clients. After successful authentication that the connection with the client is being processed, the client itself connects to the Front End.
- Billing Server is server that stores Item Mall currency information for each player.
- Item Mall is server that processes requests to buy items. Requires Billing Server.
- Master Server is server that accumulates and handle all connection between base and shards part.
- Database server is server which stores information from Account Server, Billing Server, ItemMall Server.
- Deploy/Backup server this is a deploy server, from which you have to deploy another services. Also to backup DBes from base part. Replication must be set for that by operator.
- Log Server and GM tool servers(Stats Alarm) that collects all logs from the base servers. View and statistic analysis requests are addressed through GM Tools.

```
ℹ We're looking for peoples that can create guide about GM Tools !
```

**Reason for using the base part :**

- Saving all information about accounts.
- Money and items operations.
- Servers controlling.
- Providing access for users from base part to the shard.

Shard part
---
The Allods Game Performance depends on count of shard. One shard has following servers :

- FrontEnds (2 pieces) that maintains connections with the clients after authentication. The main function of the Front End is to maintain connections with the clients playing on the shards.
- GameMechanics (3 pieces) is server that calculates the in-game mechanics, provides services for parts of the world.
- Item Server All In One or just includes all dynamic in game data: characters, guilds, mail etc.
- Deploy/Backup server this is a deploy server, from which you have to deploy another services. Also to backup DBes from shard part. Replication must be set for that by operator.
- Log Server and GM tool servers(Stats Alarm) that collects all logs from the shard servers. View and statistic analysis requests are addressed through GM Tools.

**Reason for using the base part :**

- Providing game play for the users.
- Storing avatar information.
- Storing items of avatars.
- Torrents Servers

```
ℹ We're looking for peoples that can explains more about Torrents Servers !
```

Patch Server - Server that handle the client's updates.
Torrent Tracker - Specifies the client from where the updates should be downloaded.
Torrents Seeder - Seeder to give patches for client updates.
