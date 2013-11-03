# SeriousCast

This is a SiriusXM Internet Radio to SHOUTcast bridge server.
It handles authentication and decryption of SiriusXM streams and remuxes them
into a format appropriate for standard internet radio streaming clients.

SeriousCast also offers a simple web streaming interface for all of its streams
using the VLC browser plugin.

## Requirements

SeriousCast is written in Python, and more specifically targets Python 3.3.

It has dependencies on:
* [PyCrypto](https://www.dlitz.net/software/pycrypto/)
* [Requests](http://docs.python-requests.org/en/latest/)
* [Jinja2](http://jinja.pocoo.org/docs/)

Additionally, a (non-crippled) copy of ffmpeg is required for the stream muxing.

## Setup

Make a copy of settings-example.cfg named settings.cfg. Replace the username and
password fields with your SiriusXM credentials. The hostname field should be
set to the publicly accessible hostname for your server. The ffmpeg_path field
should reflect the location of your ffmpeg binary; if it's on the PATH you
should be able to just use "ffmpeg".

After editing the configuration file, you should be able to run server.py
to start the service. Navigate to the configured port (default 30000) in a web
browser to get a list of available channels. Each channel has a "Stream" option,
which plays in your browser window, and a "Playlist" option, which downloads
a .pls file for use in your SHOUTcast player of choice.

## License

SeriousCast is licensed under the MIT (Expat) License.
