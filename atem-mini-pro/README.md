# Atem Mini Pro

## Adding Vimeo Live to ATEM Switcher Software

Install latest [ATEM Switcher Software](https://www.blackmagicdesign.com/support/family/atem-live-production-switchers) to interface with ATEM Mini Pro.

```bash
sudo vim /Library/Application\ Support/Blackmagic\ Design/Switchers/Streaming.xml
```

before the end `</streaming>` add:
```xml
<service>
        <name>Vimeo Live</name>
        <servers>
                <server>
                        <name>Primary</name>
                        <url>rtmps://rtmp-global.cloud.vimeo.com/live</url>
                </server>
        </servers>
        <profiles>
                <profile>
                        <name>Streaming High</name>
                        <config resolution="1080p" fps="60">
                                <bitrate>9000000</bitrate>
                                <audio-bitrate>128000</audio-bitrate>
                                <keyframe-interval>2</keyframe-interval>
                        </config>
                        <config resolution="1080p" fps="30">
                                <bitrate>6000000</bitrate>
                                <audio-bitrate>128000</audio-bitrate>
                                <keyframe-interval>2</keyframe-interval>
                        </config>
                </profile>
                <profile>
                        <name>Streaming Medium</name>
                        <config resolution="1080p" fps="60">
                                <bitrate>7000000</bitrate>
                                <audio-bitrate>128000</audio-bitrate>
                                <keyframe-interval>2</keyframe-interval>
                        </config>
                        <config resolution="1080p" fps="30">
                                <bitrate>4500000</bitrate>
                                <audio-bitrate>128000</audio-bitrate>
                                <keyframe-interval>2</keyframe-interval>
                        </config>
                </profile>
                <profile>
                        <name>Streaming Low</name>
                        <config resolution="1080p" fps="60">
                                <bitrate>4500000</bitrate>
                                <audio-bitrate>128000</audio-bitrate>
                                <keyframe-interval>2</keyframe-interval>
                        </config>
                        <config resolution="1080p" fps="30">
                                <bitrate>3000000</bitrate>
                                <audio-bitrate>128000</audio-bitrate>
                                <keyframe-interval>2</keyframe-interval>
                        </config>
                </profile>
        </profiles>
</service>
```

After setting this up, make sure to setup the pick the correct RTMP server and input the stream key in the output section & test it by streaming live:

![Adding stream key to Vimeo Live](images/00_streamkey.png)
