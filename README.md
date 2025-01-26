# huehuehue
My Phillips Hue experimentations

## Interact With The Bridge

```sh
export HUE_BRIDGE_IP=192.168.178.138
```

```sh
http https://${HUE_BRIDGE_IP}/clip/v2/resource/device --verify=false
```

Get an authentication token:

```sh
http POST https://${HUE_BRIDGE_IP}/api \
  --verify=false \
  devicetype="app_name#instance_name" \
  generateclientkey=true
```

```sh
http POST https://${HUE_BRIDGE_IP}/api --verify=false < request_body_request_app_token.json
```

```sh
export HUE_BRIDGE_TOKEN=
```

```sh
http https://${HUE_BRIDGE_IP}/clip/v2/resource/device \
  --verify=false \
  hue-application-key: "${HUE_BRIDGE_TOKEN}"
```

```sh
curl -X GET https://${HUE_BRIDGE_IP}/clip/v2/resource/device \
  --insecure \
  -H "hue-application-key: ${HUE_BRIDGE_TOKEN}"
```