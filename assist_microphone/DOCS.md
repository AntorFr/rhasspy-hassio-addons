# Assist Microphone

Use [Assist](https://www.home-assistant.io/voice_control/) voice control with a USB microphone.

Works with the [openWakeWord add-on](https://my.home-assistant.io/redirect/supervisor_addon/?addon=core_openwakeword)


## Installation

Click the following my button:

[![Show add-on](https://my.home-assistant.io/badges/supervisor_addon.svg)](https://my.home-assistant.io/redirect/supervisor_addon/?addon=47701997_assist_microphone&repository_url=https%3A%2F%2Fgithub.com%2Frhasspy%2Fhassio-addons)

or follow these steps to manually install the add-on:

1. Navigate in your Home Assistant frontend to **Settings** -> **Add-ons** -> **Add-on store**.
2. Add the store https://github.com/rhasspy/hassio-addons
3. Find the "porcupine1" add-on and click it.
3. Click on the "INSTALL" button.

## How to use

Before running the add-on, you must configure it with a long-lived access token from Home Assistant.
To create a token:

1. Go to your profile page in Home Assistant
2. Scroll down to **Long-lived access tokens**
3. Click **Create token**
4. Provide a name for the token and click **OK**
5. Copy the token using the **copy button** 
6. Paste the token into this add-on's configuration page
7. Click **Save** and then start the add-on

After this add-on is running, it will be automatically discovered by the Wyoming
integration in Home Assistant. To finish the setup, click the following my
button:

[![Open your Home Assistant instance and start setting up a new integration.](https://my.home-assistant.io/badges/config_flow_start.svg)](https://my.home-assistant.io/redirect/config_flow_start/?domain=wyoming)

Alternatively, you can install the Wyoming integration manually, see the
[Wyoming integration documentation](https://www.home-assistant.io/integrations/wyoming/)
for more information.

## Configuration

### Option: `token`

Long-lived access token to communicate with the Home Assistant websocket API.

This is needed because the Supervisor does not currently proxy binary websocket messages. In a future version of Home Assistant OS, this will no longer be necessary.

### Option: `vad`

Voice activity detector to use. webrtcvad is less CPU intensive, but silero is much better.

### Option: `noise_suppression`

Noise suppression level (0 is disabled, 4 is max). A value of 2 is used by default.

### Option: `auto_gain`

Automatic volume boost for microphone (0 is disabled, 31 dbfs is max). A value of 15 is used by default.

### Option: `volume_multiplier`

Multiply volume by fixed value (1.0 = no change, 2.0 = twice as loud). 1.0 is the default.

### Option: `wake_buffer_seconds`

Seconds of audio to keep for STT after wake word is detected. If you disable the `awake_sound`, it is recommended to set this value to 0.2. This will let you speak your voice command immediately after saying the wake word. 

### Option: `udp_mic`

True if audio will be sent via UDP on port 5000 (raw 16-bit 16Khz mono PCM).

### Option: `mic_device`

Number or name of microphone device (audio input). You should probably change the audio input device at the bottom of the configuration page instead of this.

### Option: `snd_device`

Number or name of sound device (audio output).  You should probably change the audio input device at the bottom of the configuration page instead of this.

### Option: `volume`

Playback volume from 0 (mute) to 1 (max).

### Option: `awake_sound`

Path to WAV file to play when wake word is detected (empty to disable).

### Option: `done_sound`

Path to WAV file to play when voice command is finished (empty to disable).

### Option: `debug_logging`

Enable debug logging.

### Option: `debug_recording_dir`

Directory to save audio for debugging purposes. Should be in /share.

## Support

Got questions?

You have several options to get them answered:

- The [Home Assistant Discord Chat Server][discord].
- The Home Assistant [Community Forum][forum].
- Join the [Reddit subreddit][reddit] in [/r/homeassistant][reddit]

In case you've found an bug, please [open an issue on our GitHub][issue].

[discord]: https://discord.gg/c5DvZ4e
[forum]: https://community.home-assistant.io
[issue]: https://github.com/home-assistant/addons/issues
[reddit]: https://reddit.com/r/homeassistant
[repository]: https://github.com/rhasspy/hassio-addons
