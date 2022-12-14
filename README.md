# tokyo-mc-22 A1 事前準備

# 以下のソフトウェアをインストールしてください

- git
- Docker
- docker-compose

# 以下の手順で docker コンテナを立ち上げてください

1. `git clone git@github.com:togswr/tmc-22-a1-docker-example`
   - ssh の設定をしていない場合 https で clone してください
     - `https://github.com/togswr/tmc-22-a1-docker-example`
2. `cd tmc-22-a1-docker-example`
3. `docker-compose build`
4. `docker-compose run --rm app sh -c 'npm install'`
5. `docker-compose up`
   - 以下のように表示されたら立ち上げ完了です
     ```
     [+] Running 2/2
     ⠿ Network tmc-22-a1-docker-example_default  Created                                                                                                                                                                                                                                   0.1s
     ⠿ Container tmc-22-a1-docker-example-app-1  Created                                                                                                                                                                                                                                   0.1s
     Attaching to tmc-22-a1-docker-example-app-1
     tmc-22-a1-docker-example-app-1  |
     tmc-22-a1-docker-example-app-1  | > src@0.1.0 dev
     tmc-22-a1-docker-example-app-1  | > next dev
     tmc-22-a1-docker-example-app-1  |
     tmc-22-a1-docker-example-app-1  | ready - started server on 0.0.0.0:3000, url: http://localhost:3000
     tmc-22-a1-docker-example-app-1  | event - compiled client and server successfully in 21.8s (161 modules)
     tmc-22-a1-docker-example-app-1  | Attention: Next.js now collects completely anonymous telemetry regarding usage.
     tmc-22-a1-docker-example-app-1  | This information is used to shape Next.js' roadmap and prioritize features.
     tmc-22-a1-docker-example-app-1  | You can learn more, including how to opt-out if you'd not like to participate in this anonymous program, by visiting the following URL:
     tmc-22-a1-docker-example-app-1  | https://nextjs.org/telemetry
     tmc-22-a1-docker-example-app-1  |
     tmc-22-a1-docker-example-app-1  | wait  - compiling / (client and server)...
     tmc-22-a1-docker-example-app-1  | wait  - compiling /_error (client and server)...
     tmc-22-a1-docker-example-app-1  | event - compiled client and server successfully in 3s (188 modules)
     ```
6. `http://localhost:3000` にブラウザでアクセスし、「Welcome to Next.js」という画面が出たら完了です
7. `Ctlr+C` でコンテナを終了させることができます

# docker のお掃除

本環境は講義では使いません。
不要な場合は、以下の「滅びの呪文」で今回作成した docker の image を削除しておきましょう。

- `docker-compose down --rmi all --volumes --remove-orphans`

参考: [《滅びの呪文》Docker Compose で作ったコンテナ、イメージ、ボリューム、ネットワークを一括完全消去する便利コマンド - Qiita](https://qiita.com/suin/items/19d65e191b96a0079417)
