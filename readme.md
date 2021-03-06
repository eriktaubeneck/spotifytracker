# Spotify Tracker

Track all the songs you listen to in the Spotify OS X app and save them in a Spotify playlist.

Living in NYC, I spend a fair amount of time underground without cell service. I also listen to a bunch of music on Spotify, and often times I'll have a song stuck in my head that isn't saved on my phone. Bad times, right? So on a Hackday, I decided to solve the problem. I created a history playlist where I would save everything I listen to. That way, when someone recommends the sweet new [St. Lucia album](https://open.spotify.com/album/4qH5TQZxM5v7tKT0E09WAK) at work, and I jam out to it, I don't have to remember to save it or something so I can listen to it on my phone underground.

## The rub

Spotify doesn't let you see what a user is currently listening to from their web api. Boo. (There's an issue open on their [web api github page](https://github.com/spotify/web-api/issues/12) that get's a +1 a day or so, if you want to join...) So instead, I hacked together some AppleScript to grab the current song from the OS X Spotify Client. So, at least for now, this is OS X only. ¯\\_(ツ)_/¯

## Installation

It's all setup with pip, so just

```
pip install spotifytracker
```

It's written in Python 3, so you'll need that installed. You'll also need to setup a Spotify Application. It's very easy, but you'll have to quickly signup for a developer account. You can create one [here](https://developer.spotify.com/my-applications/#!/applications). One you have that setup, you can create an app. You'll need to specify a callback url, but it can be anything. Once that's all set, you should create a playlist to save your songs to, and then run

```
spotifytracker setup
```

and add your username, Client ID, Client Secret, and Callback URL. You'll then authorize your app, and then be asked to pick the playlist to save your history to.

Then, to run

```
spotifytracker watch
```

## Development

To run from source, use

```
python -m spotify_tracker.runner
```

## Contribute

This was a Hackday thing, so I don't have anything specifically planned for this, but if you think it could be better, open a PR!

## License

MIT all the way.
