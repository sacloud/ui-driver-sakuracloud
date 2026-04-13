> [!CAUTION]
> **本プロジェクトは提供を終了しました**
>
> 2026年4月13日をもって、本リポジトリはアーカイブされました。  
> 本プロジェクトはすでにメンテナンスを終了しており、  
> 今後、機能追加、バグ修正、ならびにセキュリティアップデートは一切提供されません。
>
> 本プロジェクトの新規利用および継続利用は推奨されません。

# ui-driver-sakuracloud
Rancher UI driver for [SakuraCloud](https://cloud.sakura.ad.jp) docker-machine drivers

## Development

This package contains a small web-server that will serve up the custom driver UI at `http://localhost:3000/component.js`.  You can run this while developing and point the Rancher settings there.
* `npm start`
* The driver name can be optionally overridden: `npm start -- --name=sakuracloud`
* The compiled files are viewable at http://localhost:3000.
* **Note:** The development server does not currently automatically restart when files are changed.
* Do not use the `model.sakuracloudConfg` signature to access your driver config in the template file, use the `config` alias that is already setup in the component

## Building

For other users to see your driver, you need to build it and host the output on a server accessible from their browsers.

* `npm run build`
* Copy the contents of the `dist` directory onto a webserver.
  * If your Rancher is configured to use HA or SSL, the server must also be available via HTTPS.

## Using

* Add a Machine Driver in Rancher 2.0 (Global -> Node Drivers)
  * Download URL: `https://sacloud.github.io/ui-driver-sakuracloud/docker-machine-driver-sakuracloud_linux-amd64.zip`
  * Custom UI URL: `https://sacloud.github.io/ui-driver-sakuracloud/component.js`
  * Whitelist Domains: `sacloud.github.io`
* Go to Clusters -> Add Cluster, your driver and custom UI should show up.
