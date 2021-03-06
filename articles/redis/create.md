# Create a Redis Component

To add a Redis to your app, add a data component to your boxfile.yml with the `image` set to `nanobox/redis`. You should also append your image with a specific version of Redis. Available versions are listed in the [Redis Config Options guide](/redis/configure/#redis-version).

```yaml
data.redis:
  image: nanobox/redis:3.0
```

**Note:** *For purposes of these guides, we'll use* `data.redis` *as the component ID.* `redis` *is a unique identifier that can be whatever you'd like. More information about component IDs is available in the [boxfile.yml documentation](https://docs.nanobox.io/boxfile/#component-ids).*


## Configure Redis
The Redis image exposes configuration options in the boxfile.yml. These options are nested under the `config` section of your data component. For all the available configuration options, view the [Redis Config Options guide](/redis/configure).

```yaml
data.redis:
  image: nanobox/redis:3.0

  # optional redis configs
  config:
    tcp_keepalive: 60
    databases: 16
```

## Deploy
With your Redis component included in your boxfile.yml, re-run your app to create the component.

```bash
# Create a local redis component
nanobox run
```
