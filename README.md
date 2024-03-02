# Maze Generation_10_vichy_f


Japanese README

English版readmeはこちら
[README_ENGLISH](README_en.md)

このAPIはmincraft上に迷路を自動生成するためにつくられたものです。
Maze_Generation.pyを起動するとmincraft上で迷路を自動生成することができます。
※このAPIはNaohiro2g様のminecraft_remoteを使用しています。

　Naohiro2g様　https://github.com/Naohiro2g
 
　mincraft_remote https://github.com/Naohiro2g/minecraft_remote 
 
<img width="435" alt="スクリーンショット 2024-03-02 204348" src="https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/bcd89e79-4446-4b0d-82d8-9856f8ac544a">

# 自動生成するための準備
1. Forge 1.16.5をインストール
　　　https://files.minecraftforge.net/net/minecraftforge/forge/index_1.16.5.html

   ![ダウンロード (3)](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/e2e9de27-5113-4a02-807b-1e4da3dc1f91)

2. RemoteControllerMod-1.16.5 v0.05　をインストール
　　　https://www.curseforge.com/minecraft/mc-mods/remote-controller/files/3363255

    ![ダウンロード (4)](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/65c0c363-52e1-41f4-9b71-cf71aded1235)

3. mincraft(forge1.16.5)を起動

![NetherUpdateArtwork](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/28acd239-7094-43ac-8a8f-f79a9329ea85)

4. Maze_Generation.pyを実行し、迷路を生成

![Python-logo-notext svg (1)](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/89575da1-cb03-41de-bf64-c37ad86b277a)

 

===>完了！

# 迷路の詳細
　この迷路は40×40のサイズでできています。（サイズは変更可能）
　また、迷路の床と壁でブロックの種類を変更できます。（標準はダイヤモンドブロックと鉄ブロック）
　また左上と右下にスタートとゴールがあります。
　※注意
   標準では(0,5,0)あたりに生成されます。
   スーパーフラットで作成することを推奨します。
   
　<img width="435" alt="スクリーンショット 2024-03-02 204348" src="https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/f98274d1-e257-47a2-bf9b-6c349bfa00e3">


# 迷路のアルゴリズム
　このAPIでは一般的に「棒倒し法」と呼ばれるものを使用しています。
　ここでは、簡単に説明します。
 ![maze-stick03-300x300](https://github.com/vichyalpha/Maze-Generation_vichy_f/assets/107329825/d47df9f0-dc6f-4517-b529-809ce2d67134)


  # 棒倒し法の特徴
  棒倒し法は、比較的プログラミングの楽な迷路生成法です。
  また壁と道の幅が1です。

  # 作成の手順
  
   1. 迷路全体を構成する2次元配列を、幅高さ5以上の奇数で生成します。
        
   2. 迷路の外周を壁とし、それ以外を通路とします。
        
   3. 外周の内側に基準となる壁(棒)を1セルおき(x, y ともに偶数の座標)に配置します。
        
   4. 内側の壁(棒)を走査し、ランダムな方向に倒して壁とします。(ただし以下に当てはまる方向以外に倒します。)
        
      1行目の内側の壁以外では上方向に倒してはいけない。
            
       すでに棒が倒され壁になっている場合、その方向には倒してはいけない。

 # 欠点
  棒倒し法で生成された迷路は、必ず上2段の通路で左右両端への通路がつながります。
  
  これは上に倒せるのが1段目の壁のみという制約のためです。
  
  ほかにもこの上に倒せないという制約が原因で一度下がってから上がるということもあり得ません。
  
  また短い行き止まりの通路も多くなってしまいます。
  # 用途

このAPIはmincraftのmobの人工知能を実験したり、playerが遊ぶものとして最適です。

# 開発環境

python 3.11.6
 https://www.python.org/downloads/release/python-3116/
 
forge 1.16.5
 https://files.minecraftforge.net/net/minecraftforge/forge/index_1.16.5.html

RemoteControllerMod 1.16.5 v0.05

 https://www.curseforge.com/minecraft/mc-mods/remote-controller/files/3363255
