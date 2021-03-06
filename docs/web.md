# Web

*Work in progress*

source{d} Lookout web interface provides user friendly way to configure Github installations by users.

### Configuration

The web interface requires usage of Github App as authorization method and requires GitHub App OAuth credentials.

Please, follow an instraction how to get them in [main configuration guide](fix_this_link_later) and set them in `config.yaml` as following:

```yaml
providers:
  github:
    # Authorization with GitHub App
    # See https://developer.github.com/apps/building-github-apps/authenticating-with-github-apps/
    app_id: 1234
    private_key: ./key.pem
    #
    # GitHub App OAuth credentials
    client_id: 3456
    client_secret: secret-string
```

You would also need to set secret key which will be used to sign JSON Web Tokens.
It can be any non-empty string.

```yaml
web:
  # Secret key to sign JSON Web Tokens
  signing_key:
```

#### Advanced configuration

| Env var | Option | Description | Default |
| --- | --- | --- | --- |
| `LOOKOUT_WEB_HOST` | `--host` | IP address to bind the HTTP server | `0.0.0.0` |
| `LOOKOUT_WEB_PORT` | `--port` | Port to bind the HTTP server | `8080` |
| `LOOKOUT_SERVER_URL` | `--server` | URL used to access the web server in the form 'HOSTNAME[:PORT]'. Leave it unset to allow connections from any proxy or public address | |
| `LOOKOUT_FOOTER_HTML` | `--footer` | Allows to add any custom html to the page footer. It must be a string encoded in base64. Use it, for example, to add your analytics tracking code snippet | |
