# :octocat: SURENA SYSTEM

A system for professionally managing your project data
This system with a beautiful and organized user interface makes managing your project data easy and convenient,So you no longer have to worry about managing your project data

This system, along with its capabilities, creates the desired security and satisfaction for management and use for you

To better understand this system, you can pay attention to the capabilities of this system

## Build infinite score tables
## Build infinite achievements
## Manage scores and achievements from the admin panel
## Easy installation on hosts with training
## Build a reverse scoreboard
## Code to put a scoreboard or achievement in blogs
## Build infinite games
## Manage games from the admin panel
## Build infinitely variable to play
## Manage variables and data from the admin panel
## Added user section for each game
## Manage users of each game from the admin panel
## Build a version
## Select multiple administrators for the panel (this can only be done by the main administrator)
## Add or remove an administrator (this can only be done by the main administrator)
## Installing the module for the panel (almost like WordPress, which would be easy if someone wanted to write for the module panel later (because the open source panel is not provided))
## ......

:exclamation: Node Downloader only works with [NW.js](http://nwjs.io) (and [Electron](http://electron.atom.io)).
## Actions
#### Start download a file
Starts download a file.

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |
| URL       | URL of file that is to be downloaded              |
| Path      | Location that downloaded file will be saved to it |
| Name      | The name with which the file is downloaded and saved |

## Conditions
#### On completed
This event occurs once while the file downloaded and saved on the disk.

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |

___
#### On error
If the file couldn't be downloaded for any reason this event will trigger and the reason of error logs in to the console.

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |
___
#### On progress
Each file should be fragmented for downloading. After each slice of the file received, this event triggers and `Percent` expression will be accessible.

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |

## Expressions
#### Percent(tag)
Get the progress of downloading, from 0 to 100. This expression will be updated when a slice of the file received. So use it **_only_** in `On progress` event.

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |
___
#### TotalSize(tag)
Get the total size of the file, in bytes. This expression is only accessible when downloading is in progress. So you can use it in `On progress` or `On completed` events. After that, it returns `0`.

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |
___
#### downloadedsize(tag)
Get the total downloaded size of the file, in bytes. This expression is only accessible when downloading is in progress. So you can use it in `On progress` or `On completed` events. After that, it returns `0`.

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |

#### filename(tag)

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |

#### filetype(tag)

| Parameter | Explanation                                       |
| --------- | ------------------------------------------------- |
| Tag       | An optional name to distinguish between downloads |

## To do
- [x] Compatibility with google closure compiler.
- [ ] Adding more ACEs.

