# Changelog

このプロジェクトの notable な変更を記録します。  
形式は [Keep a Changelog](https://keepachangelog.com/ja/1.0.0/) に近い構成です。

## [0.2.0] — Aivis 音声合成対応

### Added

- Aivis Speech Engine 連携（ローカル HTTP API で音声合成）
- メニューから音声モデル（サムネイル付き）・スタイルを選択
- 音声モデル / スタイル選択の永続化
- Aivis Speech 接続ステータス表示（接続 OK、起動してください など）
- Aivis 未起動時の案内音声

### Changed

- AI 応答の再生を Gemini 音声から **Aivis Speech 合成音声** に変更
- Gemini Live は文字起こし（`outputAudioTranscription`）を受け取り、Aivis で TTS
- 既定の音声モデルを「コハク / ノーマル」に設定

### Removed

- メニューの Gemini プリセット声色（性別・ボイス・ピッチ）設定

### Fixed

- 音声モデル切替が反映されない問題（`AivisSpeechPlayer` の参照統一）
- タッチ音声ファイル名の Unicode 正規化による読み込み失敗

---

## [0.1.0] — 初回リリース（Gemini Live API 音声合成版）

**リリース名:** Gemini Live API で音声合成版

### Added

- Gemini Live API によるリアルタイム音声会話
- Gemini 音声のそのまま再生とリップシンク
- メニューから声色（女性 / 男性プリセット）・ピッチ変更
- VRoid Hub 連携（ハートしたモデルの取得・切り替え・クレジット表記）
- 透明ウィンドウ（`ESC` でメニュー表示と切替）
- マウス追従（体・頭・目）、`F` キーで視線固定
- 自動まばたき・待機モーション
- タッチリアクション（部位クリックで表情・短い音声）

### 必要な環境

- `~/.env` の `GEMINI_API_KEY`（Aivis Speech は不要）
