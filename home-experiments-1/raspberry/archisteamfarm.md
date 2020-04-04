# ArchiSteamFarm

## Configuration

To generate the ArchiSteamFarm config you need to fill your info [here](https://justarchinet.github.io/ASF-WebConfigGenerator/#/bot) and download the config as a json file.

You should create the following files in a config folder \( I use the `/asf` directory\) and give them root permissions.

### ASF.json

```text
{
  "s_SteamOwnerID": "<your-owner-id>",
  "AutoRestart": true,
  "IPC": true,
  "IPCPassword": null,
  "OnlineStatus": 0,
  "Headless": true
}
```

### IPC.config

```text
{
        "Kestrel": {
                "Endpoints": {
                        "HTTP": {
                                "Url": "http://*:1242"
                        }
                }
        }
}
```

### sebi\_asf.json

```text
### sebi_asf.json

{
  "SteamLogin": "<steam-user>",
  "SteamPassword": "<steam-password>",
  "Enabled": true
}
```

And run this docker command \(it will allow you to access the ASF-UI from anywhere in your lan network\)

```text
 docker run -it -p 192.168.0.114:1242:1242 -v /asf:/app/config --name asf justarchi/archisteamfarm:latest-arm
```

