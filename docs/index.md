---
hide:
  - navigation
title: Home
---
# T.e.o - The Excellent Organizer 

![Version](https://img.shields.io/badge/Latest%20Version-1.0.0.dev-%2300b4d8.svg?&style=for-the-badge&logo=git&logoColor=white)
![Python](https://img.shields.io/badge/Python-%230096c7.svg?&style=for-the-badge&logo=python&logoColor=white)
![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white)

![](./assets/poros.jpg)

## About the project
T.e.o, previously referred to as [**P.o.r.o**]("Productive Organizer and Resource Orchestrator"), is a multifunctional bot designed to enhance forum management. Its moderation and logging suite keep track of forum posting and keep your moderator accountable. Its auto-moderator capabilities also allow it to filter out certain types of queries without need for human intervention, lightening the load on the staff team. Finally, T.e.o is designed to be fast and easy to use.

## Interoperability
T.e.o is probably a useful bot for your server if:

- [x] Your server is active and needs automatic moderation
- [x] You want to give more power to your moderators
- [x] You need a long-term punishment management system

T.e.o is probably NOT the right bot for your server if:

❌ You don't already know how to use forum thread

❌ You aren't able and willing to read this wiki to solve most problems

If any of the above apply, then T.e.o will probably not be the best bot for your server, and you should consider searching on [discord.bots.gg](https://discord.bots.gg) for a different moderation bot.

## Techstack

The repository structure follows the conceptual architecture of Teobot, which consists of three loosely-coupled sub-systems.

To briefly explain these three sub-systems:

- **[Notificator](https://www.hikari-py.dev/)** employs `Hikari` utilities to catch new threads created event and directly message moderator for resolution.
- **[Storage][storage]** relies on `PostgreSQL` as a robust and feature-rich database system for persistent storage of forum queries and session log, while leveraging `SQLAlchemy` as the ORM tool for simplified interaction with the database.
- **[Logger][logger]** utilizes built-in `Logging` to record and manage thread events, errors, and messages within the server. It employs different log levels to categorize messages, providing a comprehensive overview of system activities.


## Documentation

Since Teobot is built on the basis of Hikari library, it is essential to look for the library documentation for further implementation. 

- Hikari: [hikari-py.dev](https://www.hikari-py.dev/)
- Lightbulb: [lightbulb.readthedocs.io](https://hikari-lightbulb.readthedocs.io/en/latest/)


[storage]: https://docs.python.org/3/library/sqlite3.html
[logger]: https://docs.python.org/3/library/logging.html

