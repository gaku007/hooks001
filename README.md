# 🎵 作詞サポート AI エコシステム

VS Code の Agent、Skill、Hooks を活用した、統合的な作詞サポートシステムです。

## 📋 システム概要

このプロジェクトは以下の3つのコンポーネントで構成されています：

### 1. 🤖 **Songwriting Agent** (`songwriting.agent.md`)
- **用途**: 会話形式で作詞をサポート
- **機能**:
  - 歌詞の生成と改善
  - 韻の分析と提案
  - 楽曲構成のアドバイス
  - メロディーのガイダンス
  - 感情的インパクト評価

**使用方法**:
```
チャットで直接リクエスト
"Verse about overcoming challenges を作成してください"
"この歌詞の韻の流れを改善してください"
"ポップソングの構成を提案してください"
```

### 2. 🎼 **Song Writing Skill** (`SKILL.md`)
- **用途**: `/songwrite` スラッシュコマンドでガイド付きワークフロー
- **ワークフロー**:
  1. 曲のコンセプト開発（ジャンル、ムード、テーマ）
  2. 構成計画（Verse, Chorus, Bridge など）
  3. 歌詞生成
  4. メロディーガイダンス
  5. 改善と仕上げ

**使用方法**:
```
チャットで `/songwrite` と入力
ガイド付きステップバイステップワークフローが開始
```

### 3. 📝 **File Instructions** (`lyrics.instructions.md`)
- **用途**: `.lyrics` ファイルの自動サポート
- **トリガー**: `.lyrics` ファイル を編集する際に自動的に有効化
- **機能**:
  - リアルタイム韻の分析
  - メーター＆フロー検出
  - 構造ガイダンス
  - メロディーペアリング

**使用方法**:
```
1. `mysong.lyrics` ファイルを作成
2. 歌詞を編集
3. Agent が自動的にサポートを提供
```

### 4. 🔧 **Hooks** (`songwriting-hooks.json`)
- **自動テンプレート生成**: 新しい `.lyrics` ファイルが作成されると自動的にテンプレートを挿入
- **フォーマット検証**: `.lyrics` ファイル保存時のフォーマットチェック
- **メタデータリマインダー**: メタデータ（曲名、ジャンル等）の追加を促す
- **韻スキーム分析**: 保存時に最後の Verse の韻スキームを分析
- **コンテキスト注入**: `.lyrics` ファイル開く時にメタデータを抽出

## 🎯 クイックスタート

### オプション 1: Agent との会話
```
ユーザー: "Inspirational テーマの Pop 曲を作成してください"
Agent: コンセプトから完成曲まで会話で支援
```

### オプション 2: Skill ガイドワークフロー
```
ユーザー: `/songwrite` を入力
システム: ステップバイステップで曲制作をガイド
```

### オプション 3: `.lyrics` ファイル形式
```
1. `mysong.lyrics` を作成（Hooks が自動テンプレート挿入）
2. メタデータと歌詞を編集
3. 保存時に自動検証と分析
4. Agent が改善提案を提供
```

## 📁 ファイル構造

```
.github/
├── agents/
│   └── songwriting.agent.md          # Songwriting Agent定義
├── skills/
│   └── songwriting-support/
│       ├── SKILL.md                   # Song Writing Skill
│       └── templates/
│           ├── verse-template.lyrics    # Verse テンプレート
│           ├── chorus-template.lyrics   # Chorus テンプレート
│           ├── song-structure.lyrics    # 完全楽曲構成テンプレート
│           └── rhyme-reference.lyrics   # 韻スキーム参考資料
├── instructions/
│   └── lyrics.instructions.md        # .lyrics ファイル用インストラクション
└── hooks/
    └── songwriting-hooks.json        # 自動化処理（Hook 定義）
```

## 🎓 テンプレート説明

### `verse-template.lyrics`
- Verse の構造とガイダンス
- 複数の韻スキーム例（AABB, ABAB, ABCB）
- メロディーフロー指針
- 感情的進行ガイド
- イメージ強化のコツ

### `chorus-template.lyrics`
- Chorus の構造ガイド
- 強力な Chorus の例
- Hook 配置戦略
- メロディー特性
- よくある間違いと対策

### `song-structure.lyrics`
- 完全な楽曲構成テンプレート
- セクション別のタイミング（3:00-3:30 standard）
- 感情的アーク図
- ジャンル別調整（Pop, Rock, Hip-Hop, Ballad, Jazz/Soul）
- 完成チェックリスト

### `rhyme-reference.lyrics`
- 韻の種類解説（完全韻、Slant 韻、頭韻等）
- 韻スキーム体系（AABB, ABAB, ABCB, AAAA等）
- 韻の配置テクニック
- ジャンル別韻テクニック推奨
- 高度な韻テクニック
- 練習エクササイズ

## 💡 よくある使用シナリオ

### シナリオ 1: 新しい曲を最初から作成
```
1. /songwrite スラッシュコマンドを実行
2. ガイド付きワークフローに従う
3. 各セクション（Verse, Chorus, Bridge）を生成
4. メロディーガイダンスを受ける
5. 完成曲を出力
```

### シナリオ 2: 既存の歌詞を改善
```
1. mysong.lyrics ファイルを開く
2. Agent に改善箇所をリクエスト
3. "韻スキームを改善してください" など具体的に指示
4. Agent の提案に基づき編集
5. 繰り返して完璧に
```

### シナリオ 3: 特定の技法を学ぶ
```
1. rhyme-reference.lyrics を確認
2. 特定の韻スキーム例を学習
3. 自分の曲に適用
4. テンプレートを参考に実践
```

### シナリオ 4: ジャンル別作詞
```
1. song-structure.lyrics でジャンル別構成を確認
2. /songwrite で開始、ジャンル選択
3. ジャンル別推奨事項に基づき制作
```

## 🎼 `.lyrics` ファイルフォーマット

```lyrics
SONG: Song Title
ARTIST: Artist Name
KEY: C Major
TEMPO: 120 BPM
GENRE: Pop
MOOD: Inspirational
THEME: Main theme or story description

[VERSE 1]
Your first verse lyrics here
Multiple lines per verse

[PRE-CHORUS]
Optional building section

[CHORUS]
Your main hook and chorus

[VERSE 2]
Second verse lyrics

[BRIDGE]
Contrasting section

[OUTRO]
Closing section
```

## 🔄 Hooks が自動的に行うこと

1. **新規ファイル作成時**
   - テンプレート自動挿入
   - メタデータスタブ自動生成
   - セクションサンプル自動作成

2. **ファイル保存時**
   - フォーマット検証
   - 韻スキーム分析
   - セクション構成チェック

3. **ファイル開く時**
   - メタデータ抽出
   - Context に曲情報注入
   - Agent の理解度向上

## 🎵 機能詳細

### Agent の機能
- ✅ 歌詞の生成
- ✅ 韻の分析と提案
- ✅ メーター＆フロー検出
- ✅ 楽曲構成アドバイス
- ✅ メロディーペアリング
- ✅ 感情的インパクト評価
- ✅ 改善提案

### Skill の機能
- ✅ ガイド付きコンセプト開発
- ✅ 構成計画ウィザード
- ✅ ステップバイステップ歌詞生成
- ✅ メロディーガイダンス
- ✅ 完成チェックリスト

### File Instructions の機能
- ✅ セクションタイプ認識
- ✅ リアルタイム韻分析
- ✅ 構造検証
- ✅ メロディー提案
- ✅ メタデータ管理

## 🎯 ベストプラクティス

1. **メタデータを常に含める**: 曲名、ジャンル、ムード等は Agent の理解度を大幅に向上させます
2. **テンプレートから開始**: テンプレートは業界標準に基づいて設計されています
3. **何度も反復**: 最初のドラフトは常に改善の余地があります
4. **音声でテスト**: 歌詞は必ず音読/歌唱してテストしてください
5. **参考資料を学習**: `rhyme-reference.lyrics` で技法を学び、実践に応用
6. **ジャンル研究**: 目標ジャンルの成功曲を分析してください

## 🚀 次のステップ

1. **初めての曲作成**:
   ```bash
   1. `mysong.lyrics` ファイルを作成
   2. テンプレートが自動挿入される
   3. メタデータを入力
   4. Agent に改善を依頼
   ```

2. **スキルを深める**:
   ```bash
   1. `/songwrite` で複数の曲を制作
   2. テンプレートから本テンプレートまで段階的に学習
   3. 各ジャンルで実践
   ```

3. **高度な技法**:
   ```bash
   1. rhyme-reference.lyrics で韻技法を研究
   2. song-structure.lyrics でジャンル別構成を学習
   3. 複雑な曲構成に挑戦
   ```

## 📞 トラブルシューティング

### Agent が応答しない
- `.lyrics` ファイルにメタデータが含まれているか確認
- チャットで明確に指示を与える
- 具体的なリクエスト（"韻を改善"等）をする

### Hooks が自動実行されない
- ファイルが `.lyrics` 拡張子であることを確認
- VS Code をリロード
- `.github/hooks/songwriting-hooks.json` が正しくフォーマットされているか確認

### テンプレートが挿入されない
- `.lyrics` ファイルが空ファイルか確認
- Hooks の `FileCreated` イベント設定を確認

## 🎓 学習リソース

- **テンプレート**: `.github/skills/songwriting-support/templates/` 内の全ファイル
- **ジャンル別ガイド**: `song-structure.lyrics` の「GENRE-SPECIFIC ADJUSTMENTS」
- **韻の全ガイド**: `rhyme-reference.lyrics`
- **Agent ドキュメント**: `.github/agents/songwriting.agent.md`

---

**バージョン**: 1.0  
**最終更新**: 2026年5月31日  
**対応言語**: 日本語 & 英語