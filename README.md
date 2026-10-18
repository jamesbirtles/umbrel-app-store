# James Birtles Umbrel App Store

A community app store for [umbrelOS](https://umbrel.com), hosted at
https://github.com/jamesbirtles/umbrel-app-store. Its store ID is `jamesbirtles`;
every app ID must start with `jamesbirtles-`.

This store does not contain any apps yet. Add an app before installing the
store on umbrelOS.

## Add an app

1. Create a directory named `jamesbirtles-<app-name>`.
2. Add an `umbrel-app.yml` with the same `id` and accurate listing details.
   See the [Umbrel App Store packages](https://github.com/getumbrel/umbrel-apps)
   for packaging examples.
3. Add a `docker-compose.yml` for the app's services. When using `app_proxy`,
   set `APP_HOST` to `jamesbirtles-<app-name>_<service-name>_1` and `APP_PORT`
   to the service's internal listening port. Set the manifest's `port` to
   the port umbrelOS should open in the browser.
4. Commit and push the package. In umbrelOS, add
   `https://github.com/jamesbirtles/umbrel-app-store` as a community app store,
   or refresh it if already added.

For packaging requirements and platform conventions, see the
[Umbrel App Store documentation](https://github.com/getumbrel/umbrel-apps).
