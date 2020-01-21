This container is based on gists/mpd (https://www.github.com/vgist/dockerfiles) it is changed to work with a local soundcard on Torizon and is tested on a Colibri iMX8X from Toradex.

#### Volume

- /var/lib/mpd

#### Custom usage:

docker run \
	-d \
	--rm \
	--name mpd \
	--device /dev/snd \
	-p 6600:6600 \
	-v /home/torizon/music/:/var/lib/mpd/music \
	-v /home/torizon/playlists/:/var/lib/mpd/playlists \
	-v /var/lib/alsa/:/var/lib/alsa/ \
	philschenker/mpd

#### Compose example:

    mpd:
      image: philschenker/mpd
      ports:
        - "6600:6600"
      volumes:
        - /your/music:/var/lib/mpd/music
      devices:
        - /dev/snd
      restart: always

### Client

- mpc: <http://www.musicpd.org/clients/mpc/>
- ncmpc: <http://www.musicpd.org/clients/ncmpc/>
- nncmpp: <https://git.janouch.name/p/nncmpp/>

