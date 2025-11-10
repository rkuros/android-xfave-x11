# Android Xfce X11

Termux:X11を使用してAndroidデバイス上でXfce4デスクトップ環境を起動するスクリプトです。

## 必要な環境

- Termux
- Termux:X11アプリ
- proot-distro
- Ubuntu（proot-distro経由）

## インストール

### 1. Termux:X11のインストール

[Termux:X11](https://github.com/termux/termux-x11)をインストールしてください。

### 2. 必要なパッケージのインストール

```bash
pkg install termux-x11-nightly proot-distro
```

### 3. Ubuntuのインストールと設定

```bash
proot-distro install ubuntu
proot-distro login ubuntu -- bash -c "apt update && apt install -y xfce4 xfce4-terminal dbus-x11"
```

### 4. スクリプトのダウンロード

```bash
curl -O https://raw.githubusercontent.com/rkuros/android-xfave-x11/main/x11
chmod +x x11
```

## 使い方

スクリプトを実行するだけです：

```bash
./x11
```

スクリプトは以下を自動的に実行します：

1. Termux:X11アプリを起動
2. termux-x11サーバーを開始（必要な場合）
3. proot-distro経由でUbuntu環境にログイン
4. D-Busセッションを開始
5. Xfce4デスクトップコンポーネント（ウィンドウマネージャー、デスクトップ、パネル、ターミナル）を起動

## 注意事項

- 初回起動時は少し時間がかかる場合があります
- Termux:X11アプリが正しくインストールされていることを確認してください
- セッションを終了するには、Termux:X11アプリを閉じるか、Termuxでプロセスを停止してください

## ライセンス

MIT License
