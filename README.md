# Raw Sounds of Endless Sky

This repository contains raw uncompressed music for the plugin [sounds of
endless sky][1].

# Music by Anthrophantasmus

Licensed CC-BY-4.0.  See [copyright](copyright) for licensing.

Other profiles:

- Music under [original/music/ByAnthrophantasmus](original/music/ByAnthrophantasmus)
- [Anthrophantasmus YouTube channel][Anthrophantasmus-youtube]
- [Anthrophantasmus GitHub profile][Anthrophantasmus-github]

[Anthrophantasmus-youtube]: https://www.youtube.com/channel/UCryMx7RshwDKNHQ-amgEm0A
[Anthrophantasmus-github]: https://github.com/Anthrophantasmus

# Music by Thorne11

Licensed CC-BY-4.0.  See [copyright](copyright) for licensing.

Other profiles:

- Music under [original/music/ByThorne11](original/music/ByThorne11)
- Copied with permission from [ES-Ambience][ES-Ambience].
- [Thorne11 Bandcamp profile][Thorne11-bandcamp]
- [Thorne11 GitHub profile][Thorne11-github]

[ES-Ambience]: https://github.com/Thorne11/ES-Ambience
[Thorne11-bandcamp]: https://horrowithl.bandcamp.com/track/generative-ambient-test-track
[Thorne11-github]: https://github.com/Thorne11

# Audio conversion

Endless Sky is extremely specific about how it supports audio.  Currently, only
WAV for sound effects and MP3 for music is supported.

### Encoding sound effects

Sound effects are in WAV format.  Specifically, little-endian 16-bit PCM at
44100 Hz.

Here's an `ffmpeg` command to get sounds into an appropriate format.

    ffmpeg -i original.wav -ac 1 -f wav -c pcm_s16le -ab 705k -ar 44100 sounds/effect.wav

### Encoding music

MP3 specifically requires stereo format (2-channel) bit rate 179kb/s at 44100
Hz.

    ffmpeg -i original.wav -f mp3 -ar 44100 -ab 179k -ac 2 sounds/music.mp3
