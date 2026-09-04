<div align="center">

<img src="logo/alauda_lockup.svg" alt="Alauda" width="420">

**foobar2000 用 多機能 DSP コンポーネント**

[![Platform](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#動作環境)
[![Host](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![License](https://img.shields.io/badge/license-proprietary%20freeware-green)](#ライセンス)

[製品ページ](https://moenium.net/alauda/) ·
[マニュアル](https://moenium.net/alauda/manual/1.0/) ·
[GitHub Releases](../../releases/latest) ·
[BOOTH](https://moenium.booth.pm/items/8779312) ·
[更新履歴](distribution/changelog.md) ·
[English README](README.md)

</div>

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.png" alt="Support Alauda on Ko-fi" width="1000">
  </a>
</p>

<p align="center">
  <a href="https://ko-fi.com/moenium"><strong>🦊 Ko-fiでAlaudaを応援してください 🎵</strong></a>
</p>

---

Alauda は foobar2000 の再生チェーンの中に入り、出力デバイスへ向かう音声を加工する多機能 DSP コンポーネントです。

自分好みの音で音楽を聴くためのさまざまなツール、リサンプリング、音色づくり、サチュレーション、EQ、リバーブ、ステレオ定位、ヘッドホン補正、出力保護などを、ひとつのプラグインにまとめています。

13 の処理ステージが決まった順序で並び、それぞれを個別に有効にできます。初期状態は意図的にほぼ無効です。リサンプラーを含むほとんどのステージが無効から始まるため、インストール直後に音が変わらないのは正常な動作です。

<div align="center">
<img src="screenshots/alauda_screenshot/16_navigation_pinned.png" alt="Alauda 設定画面 - Resampler ページ" width="720">
</div>

## 目次

- [主な機能](#主な機能)
- [信号の流れ](#信号の流れ)
- [スクリーンショット](#スクリーンショット)
- [動作環境](#動作環境)
- [インストール](#インストール)
- [使いはじめ](#使いはじめ)
- [ダウンロードと検証](#ダウンロードと検証)
- [ドキュメント](#ドキュメント)
- [プリセットと言語](#プリセットと言語)
- [このリポジトリについて](#このリポジトリについて)
- [フィードバック・不具合報告](#フィードバック不具合報告)
- [ライセンス](#ライセンス)

## 主な機能

- **13 ステージをひとつの画面に。** 各ステージは独立して個別に有効化できます。処理順序は固定されているため、信号の流れを把握しやすくなっています。
- **リサンプラー** ダイレクト / カスケード変換、4 種の位相モード、選択可能なフィルター品質。
- **17 種のリバーブ空間** アンビエンスからプレート系まで対応し、初期反射も調整できます。
- **24 種のサチュレーション・キャラクター** テープ速度や真空管トポロジーを含む複数の特性を選択できます。
- **8 バンド パラメトリック EQ** 22 種のプリセットと複数のフィルタータイプ。
- **ヘッドホン処理** クロスフィード、バーチャルスピーカー、10 バンドの Headphone Match 補正。
- **10 種のジャンルプロファイル** 複数のステージへまとめて設定を適用します。
- **出力ステージ** ラウドネス合わせ、オートヘッドルーム、セーフティリミッター、ディザ。
- **3 種のテーマ** ライト / ダーク / ハイコントラスト。
- 表示は日本語・英語に対応し、追加の翻訳ファイルも読み込めます。
- 設定は foobar2000 のプロファイルに保存されるため、Alauda の更新後も残ります。また、どのページからでも設定をファイルへ書き出したり、読み込んだりできます。

## 信号の流れ

| セクション | ステージ |
| --- | --- |
| レート | リサンプラー |
| メインチェーン | 波形再構成 · ダイナミクス復元 · エンハンス · アナログ感 · サチュレーション · EQ · リバーブ |
| 補正 | 仕上げ補正（サブソニック / 超音波 / 疲労ガード） |
| 定位 | ステレオ定位 · ヘッドホン · ヘッドホン・マッチ |
| 保護 | 出力（ラウドネス合わせ / ヘッドルーム / リミッター / ディザ） |

foobar2000 の **Active DSPs** 内での並び順も結果に影響します。

Alauda より前に置かれた DSP の出力は Alauda に入力され、Alauda より後ろに置かれた DSP は Alauda の出力を処理します。

## スクリーンショット

| プロファイル | サチュレーション |
| --- | --- |
| ![プロファイル](screenshots/alauda_screenshot/01_profiles_compact.png) | ![サチュレーション](screenshots/alauda_screenshot/07_saturation_compact.png) |

| リバーブ | ヘッドホン |
| --- | --- |
| ![リバーブ](screenshots/alauda_screenshot/09_reverb_compact.png) | ![ヘッドホン](screenshots/alauda_screenshot/12_headphone_compact.png) |

<details>
<summary><strong>その他のスクリーンショット</strong></summary>

<br>

| リサンプラー | 波形再構成 |
| --- | --- |
| ![リサンプラー](screenshots/alauda_screenshot/02_resampler_compact.png) | ![波形再構成](screenshots/alauda_screenshot/03_reconstruction_compact.png) |

| ダイナミクス復元 | エンハンス |
| --- | --- |
| ![ダイナミクス復元](screenshots/alauda_screenshot/04_dynamics_compact.png) | ![エンハンス](screenshots/alauda_screenshot/05_enhance_compact.png) |

| アナログ感 | EQ |
| --- | --- |
| ![アナログ感](screenshots/alauda_screenshot/06_analog_compact.png) | ![EQ](screenshots/alauda_screenshot/08_eq_compact.png) |

| 仕上げ補正 | ステレオ定位 |
| --- | --- |
| ![仕上げ補正](screenshots/alauda_screenshot/10_refine_compact.png) | ![ステレオ定位](screenshots/alauda_screenshot/11_stereo_image_compact.png) |

| ヘッドホン・マッチ | 出力 |
| --- | --- |
| ![ヘッドホン・マッチ](screenshots/alauda_screenshot/13_headphone_match_compact.png) | ![出力](screenshots/alauda_screenshot/14_finish_compact.png) |

| ダークテーマ | ハイコントラストテーマ |
| --- | --- |
| ![ダークテーマ](screenshots/alauda_screenshot/17_theme_dark.png) | ![ハイコントラストテーマ](screenshots/alauda_screenshot/18_theme_high_contrast.png) |

</details>

## 動作環境

| | |
| --- | --- |
| OS | Windows |
| ホスト | foobar2000 v2.x（**64bit 版のみ**） |
| CPU | x86-64（Intel / AMD） |
| 出力 | foobar2000 が開けるオーディオデバイス |
| 追加ランタイム | 不要 |

32bit 版の foobar2000 には対応していません。32bit 版では DSP Manager にコンポーネントが表示されません。

処理負荷は、有効にしたステージと処理時のサンプルレートによって変わります。特に、リサンプラーの高い倍率と高品質フィルターの組み合わせは大きな負荷要因です。再生が安定しない場合は、まずこの 2 つの設定を見直してください。

高い倍率でリサンプリングする場合は、その結果のサンプルレートを受け付ける出力デバイスも必要です。

## インストール

1. foobar2000 を終了します。
2. `foo_dsp_alauda.fb2k-component` をダブルクリックします。または **File → Preferences → Components** を開き **Install…** を選びます。
3. **Apply** を選ぶと foobar2000 が再起動し、インストールが完了します。

コンポーネントをインストールしただけでは再生チェーンには入りません。

4. **File → Preferences → Playback → DSP Manager** を開きます。
5. **Alauda** を **Active DSPs** に移動します。
6. **Configure selected** で設定画面を開きます。
7. **Apply** を選びます。

### アンインストール

**Active DSPs** から Alauda を外し、**Preferences → Components** で **Alauda DSP** を削除して **Apply** を選びます。

ご自身で言語フォルダーへ追加した翻訳ファイルはそのまま残ります。

## 使いはじめ

まずは [オンラインマニュアル](https://moenium.net/alauda/manual/1.0/) の **クイックスタート**からお読みください。数分で安全な初期設定まで進められます。

設定画面の **Help** コマンドを使うと、現在表示しているページに対応したオンラインマニュアルを開けます。

> **始める前に再生音量を下げてください。** ピークレベルや音量感を変えるステージが複数あります。出力ページの保護機能であるオートヘッドルームとセーフティリミッターは初期状態では無効です。必要に応じて有効にしてください。

> **クロスフィードとバーチャルスピーカーはヘッドホン専用です。** スピーカー再生では左右の音が空間を通じて両耳へ自然に届くため、これらの処理をさらに加えると、定位が狭くなったり不自然に聞こえたりすることがあります。スピーカーで聴くときはヘッドホンページを無効にしてください。

## ダウンロードと検証

Alauda の最新版は
[GitHub Releases](https://github.com/moenium-AI/Alauda/releases/latest)
または [BOOTH](https://moenium.booth.pm/items/8779312)
から入手できます。

各 GitHub Release には、そのリリースの配布ファイル名、チェックサム、VirusTotal のスキャン結果を掲載します。

ダウンロードしたファイルを検証する場合は、ファイルのハッシュを計算し、該当するリリースページに記載された値と照合してください。

Windows PowerShell では、次のコマンドで SHA-256 を確認できます。

```powershell
Get-FileHash .\Alauda_*.zip -Algorithm SHA256
```

チェックサムが一致すれば、ダウンロードしたファイルが該当リリースで示されたファイルと同一であることを確認できます。

## ドキュメント

- [オンラインマニュアル（日本語 / English）](https://moenium.net/alauda/manual/1.0/)
  - 各処理ステージの詳細
  - 全パラメーターの既定値と範囲
- [更新履歴](distribution/changelog.md)
- [同梱 README（日本語）](distribution/readme.txt)
- [同梱 README（English）](distribution/readme_en.txt)
- [EULA（日本語）](distribution/EULA_jp.txt)
- [EULA（English）](distribution/EULA_en.txt)
- [サードパーティー表記](distribution/third-party-notices.txt)

## プリセットと言語

**Preset Pack Vol.1 / Vol.2** は、Alauda の設定を試しやすくするための追加プリセット集です。

Alauda 本体の機能を追加したり制限したりするものではありません。公式配布ではコンポーネント本体とは別に収録されています。必要に応じて解凍してお使いください。

### 日本語表示

日本語表示は任意です。

配布アーカイブの `Languages\ja-JP.lng` を、foobar2000 の **Profiles → Open Folder** で開くフォルダー内の `languages` フォルダーへコピーしてください。

Alauda は翻訳ファイルをコンポーネント DLL の隣ではなく、foobar2000 のプロファイルから読み込みます。

### 試作言語ファイル

`Languages/experimental/` には、次の言語の試作ファイルを収録しています。

- ドイツ語
- フランス語
- スペイン語
- イタリア語
- ブラジルポルトガル語
- ロシア語
- 簡体字中国語
- 繁体字中国語
- 韓国語

これらは正式な翻訳ではなく、ネイティブ話者による用語、表現、実際の画面での表示幅などの確認を目的としたレビュー用ファイルです。

公式の配布 ZIP には含まれていません。

試す場合は、対応する `.lng` ファイルを上記の `languages` フォルダーへコピーし、Alauda から選択してください。

固定幅の UI に収めるため、短い表現や音響分野で一般的な英語用語を意図的に使用している箇所があります。

翻訳を確認するときは、表現が自然かどうかだけでなく、実際の設定画面で文字が切れないかも確認してください。

修正案を報告する際は、次の情報を添えてください。

- 言語
- キー名
- 現在の文言
- 提案する文言

## フィードバック・不具合報告

不具合報告、翻訳の修正提案、その他のフィードバックを受け付けています。

**contact@moenium.net**

## ライセンス

Alauda は**プロプライエタリなフリーソフトウェア**です。個人・業務・商用を問わず無償でご利用いただけます。

言語ファイルとプリセットファイルを除く、プラグイン本体および構成ファイルの再配布は禁止です。

言語ファイル・プリセットファイルの再配布を含むその他すべての条件は、同梱の [EULA_jp.txt](distribution/EULA_jp.txt) / [EULA_en.txt](distribution/EULA_en.txt) に定めます。

この README は概要のみを示すものであり、EULA の内容を変更するものではありません。

### 同梱のサードパーティーソフトウェア

- **JUCE 9.0.1**（JUCE 9 Starter ライセンス）Raw Material Software Limited。設定画面の構築に使用しており、Alauda 自身のライセンスではなく JUCE 9 エンドユーザーライセンス契約に従います。Windows ビルドには zlib、libpng、Independent JPEG Group の JPEG ソフトウェア、HarfBuzz、SheenBidi、LunaSVG、PlutoVG も、それぞれのライセンスのもとで含まれます。
- **foobar2000 SDK** foobar2000 プロジェクトの定める条件に従います。foobar2000 本体は Alauda の一部ではなく、同梱もしていません。

詳細は [third-party-notices.txt](distribution/third-party-notices.txt) をご覧ください。

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
