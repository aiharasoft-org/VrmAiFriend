# v0.8.0 — Windows 対応

**リリース名:** Windows 対応  
**対象プラットフォーム:** **Windows**、**macOS**（Windows 版を新規追加）

**Windows 版** が初めてリリースされました。macOS 版は従来どおり利用できます。あわせて、音声の話速調整、マイク入力の安定化、設定タブでのマイク状態表示、OS 別のカメラ操作ガイドなど、Windows 移植に伴う UX を整えています。

## ハイライト

- **Windows 対応（本リリースの主題）** — 初の Windows ビルド。Aivis Speech の検出・起動、透過ウィンドウ
- **話速スライダー** — 音声タブで 0.8〜1.5 を調整（既定 1.0、永続化）
- **設定タブのマイク状態** — 物理マイクの有無・権限・入力状態を表示
- **マイク入力の安定化** — 高サンプルレート取得、自動再試行、感度の自動更新
- **マイクメータ改善** — 実測に合わせた動的スケールと閾値表示
- **OS 別カメラガイド** — Windows: Alt / Ctrl、macOS: Option / Cmd
- **Windows CPU 向け Tips** — README に電源モード「最適なパフォーマンス」の案内

## ダウンロード

| プラットフォーム | ファイル（手動アップロード予定） |
| ---------------- | -------------------------------- |
| **Windows** | `VrmAiFriend-Windows.zip`（展開後 `.exe` を実行） |
| **macOS** | `VrmAiFriend-macOS.zip`（`.app` を起動） |

## インストール

### 共通（Windows / macOS）

| 項目 | 内容 |
| ---- | ---- |
| Aivis Speech Engine | 必須。[AivisSpeech Engine](https://github.com/Aivis-Project/AivisSpeech-Engine) をインストールし起動 |
| Gemini API キー | **設定** タブで保存 |
| 物理マイク | 必須（仮想オーディオのみでは不可） |

### Windows

1. **Windows 版** をダウンロードし、ZIP を展開する。
2. フォルダ内の **`.exe`** を実行する。

**SmartScreen / セキュリティ警告（未署名アプリ）**

GitHub から取得した Windows 版はコード署名がないため、初回起動時に **Microsoft Defender SmartScreen** がブロックすることがあります（「Windows によって PC が保護されました」「不明な発行元」など）。

信頼できる配布元であることを確認したうえで、次のいずれかで起動してください。

| 方法 | 手順 |
| ---- | ---- |
| 起動ダイアログ | **詳細情報** → **実行** |
| ブロック解除（推奨） | `.exe` の **プロパティ** → **全般** → **ブロックの解除** にチェック → **OK** → 再実行 |

**Aivis Speech（Windows）:** [AivisSpeech](https://github.com/Aivis-Project/AivisSpeech) 本体または Engine のいずれかをインストール。**Engine 接続 OK** なら利用可能。

### macOS

1. **macOS 版** をダウンロードする。
2. `.app` を起動する。Gatekeeper で止まる場合は **Control + クリック** → **開く**、または **システム設定** → **プライバシーとセキュリティ** から許可する。
3. **AivisSpeech Engine** をインストールし、**マイク** 権限を OS 設定で許可する。

## 設定タブのマイク状態

**設定** タブでは GEMINI → VRoid Hub → **マイク** → Aivis Speech の順で状態を表示します。

| 表示 | 意味 |
| ---- | ---- |
| `OK` | 物理マイクから音声を取得中 |
| `準備完了` | 物理マイクあり・権限 OK（未キャプチャ） |
| `物理マイクが見つかりません` | 仮想オーディオ（VB-Audio 等）のみ、または実マイクなし |
| `権限なし` | OS のマイク権限が未許可 |

> **Windows:** VB-Audio Virtual Cable などの仮想デバイスだけが入っている PC では **物理マイクが見つかりません** と表示されます。

## 必要な環境

| 項目 | 内容 |
| ---- | ---- |
| OS | **Windows** または **macOS** |
| 物理マイク | 必須 |
| Aivis Speech Engine | 音声合成に必須 |
| Gemini API キー | **設定** タブで保存 |

## アップグレード時の注意（v0.7 → v0.8）

- **Windows 版は新規対応**（本リリースの主題）。macOS 版の既存データ（記憶・好感度・音声設定など）は同じ形式で利用可能
- 話速は未設定時 **1.0**
- マイク感度を調整済みの場合、**マイク感度調整** のやり直しを推奨
- 仮想オーディオ（VB-Audio 等）のみの環境では **物理マイクが見つかりません** と表示される

詳しい使い方は [README.md](https://github.com/aiharasoft-org/VrmAiFriend/blob/main/README.md)、全バージョンの変更一覧は [CHANGELOG.md](https://github.com/aiharasoft-org/VrmAiFriend/blob/main/CHANGELOG.md) を参照してください。
