# Healthcan
## Name
- ~ Healthcan ~
  - Health：健康
  - Scan：調べる
  - Can：管理

## Overview
- Python（Tornado） + Docker を利用して健康管理アプリケーションを制作
- 身長, 体重を入力するとBMIや適正体重などを算出してグラフ表示する
  - 体重の変化などが一眼でわかる
- 基本機能
  - アカウント管理
  - データ追加
  - データ管理
  - グラフ可視化

## Description
- 環境構築
  ```
  ### コンテナ用のネットワークを作成
  $ docker network create healthcan_link

  ### ビルド & 実行
  $ docker-compose up -d --build

  ### JupyterNotebook コンテナに入る
  $ docker-compose exec jupyternotebook bash
  OR
  $ docker exec -it healthcan_jupyternotebook_1 /bin/bash
  ```
- 実行
  ```
  a. ビルド時のみ
  ### データベースへの接続 && カーソルの生成
  # python hc_server.py migrate

  b. 2回目以降
  ### docker-compose を起動させるだけ
  $ docker-compose start
  ```
- アクセス
  - Healthcan
    - http://localhost:3000/
  - JupyterNotebook  
    - http://localhost:8888/

## CodeTest
- `# python -m unittest [フォルダ].[ファイル].[クラス].[テスト関数]`
  - 例：）`# python -m unittest tests.test_hero.test_hero.test_is_valid`

## Other：Docker Command
- docker
  ```
  ### ステータス確認
  $ docker ps
  
  ### コンテナリスト
  $ docker ps -a
  
  ### 起動
  $ docker start [コンテナ名]
  
  ### 停止
  $ docker stop [コンテナ名]
  
  ### 再起動
  $ docker restart [コンテナ名]
  
  ### コンテナ削除
  $ docker rm [コンテナ名]
  
  ### イメージリスト
  $ docker images
  
  ### イメージ削除
  $ docker rmi [イメージID]
  
  ### コンテナログ
  $ docker logs [コンテナ名]

  ### イメージヒストリ
  $ docker history [イメージ名]
  ```
 - docker-compose
   ```
   ### 起動
   $ docker-compose start
   
   ### 停止
   $ docker-compose stop
   
   ### 再起動
   $ docker-compose restart
   
   ### コンテナ & イメージ をまとめて削除
   $ docker-compose down
   
   ### キャッシュを使用しずにビルド（更新したDockerfile, yamlなどを反映させる）
   $ docker-compose build --no-cache

   ### ビルド & 実行
   $ docker-compose up -d --build

   ### コンテナに入る
   $ docker exec -it [コンテナ名] /bin/bash
   
   ### 詳細表示
   $ docker-compose config
    
   ### ステータス確認
   $ docker-compose ps 

   ### インスタンスログ
   $ docker-compose logs
   ```
- docker network
  ```
  ### ネットワークの作成
  $ docker network create [ネットワーク名]
  
  ### ネットワークの詳細表示
  $ docker network inspect [ネットワークID]    
  
  ### ネットワークの一覧表示
  $ docker network ls
  
  ### 既存ネットワークの削除
  $ docker network rm [ネットワークID]
  ```
