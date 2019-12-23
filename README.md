# xiaomi-vacuum
My modifications to xiaomi vacuum

## Usage

You need to have python3 and pip installed.

```
pip3 install python-miio
```

Check if you can get to the vacuum automatically

```
mirobo discover --handshake 1
```

If token is different from `0`s and `f`s then you're ready to go. If not I used this https://python-miio.readthedocs.io/en/latest/discovery.html#tokens-from-backups on Iphone SE iOS 12 and it works perfectly.

```
export MIROBO_IP=... # IP of the vacuum
export MIROBO_TOKEN=... # Token of the vacuum, see below
```

And test the connection

```
mirobo sound --test
```

The you can install the sound

```
mirobo install-sound your-voice-pack.pkg
```


