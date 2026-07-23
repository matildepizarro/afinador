<div align="center">

# 🎸 Afinador de Matilde

**Afinador cromático de guitarra y bajo, 100% en el navegador — sin instalar nada.**

[![Static Site](https://img.shields.io/badge/tipo-HTML%20%2B%20CSS%20%2B%20JS-ff3d97?style=for-the-badge)](#)
[![No build step](https://img.shields.io/badge/build-no%20necesario-2fd6a4?style=for-the-badge)](#)
[![Idiomas](https://img.shields.io/badge/idiomas-ES%20%7C%20EN%20%7C%20PT%20%7C%20JA-efb8ea?style=for-the-badge)](#)
[![License: MIT](https://img.shields.io/badge/licencia-MIT-lightgrey?style=for-the-badge)](#-licencia--license--licença--ライセンス)

**[🇪🇸 Español](#-español)** · **[🇬🇧 English](#-english)** · **[🇧🇷 Português](#-português)** · **[🇯🇵 日本語](#-日本語)**

</div>

---

<br>

## 🇪🇸 Español

### ¿Qué es esto?

**Afinador de Matilde** es un afinador cromático de guitarra y bajo que corre **completamente en el navegador**, con detección de tono en tiempo real, una biblioteca enorme de afinaciones (incluyendo afinaciones usadas por bandas reales), reproducción de cuerdas con síntesis física, y un módulo completo de **grabación multipista de alta fidelidad**. No requiere backend, no requiere instalación ni build: es un único archivo HTML.

> 🔒 **Privacidad primero**: todo el procesamiento de audio ocurre localmente en tu navegador. El micrófono nunca se envía a ningún servidor.

### ✨ Funcionalidades

#### 🎯 Afinador en tiempo real
- Detección de tono con algoritmo **YIN** (autocorrelación) sobre `AnalyserNode` de Web Audio API, optimizado para notas graves (bajos de 6 cuerdas, drop tunings).
- Aguja/gauge visual estilo pedal de efectos, con lectura en **centésimas (cents)** y color que cambia a verde cuando la nota está afinada.
- Nombre de nota grande y legible, con indicador de si está justa, sostenida o bemol respecto al objetivo.
- **Modo cromático libre**: detecta cualquier nota, sin importar la afinación elegida — útil para afinar instrumentos fuera de las afinaciones predefinidas.
- Referencia **A4 calibrable** (438–445 Hz) para adaptarse a orquestas o gustos personales.

#### 🎻 Instrumentos y afinaciones
- Instrumentos soportados: **guitarra de 6 cuerdas, guitarra de 7 cuerdas, bajo de 4, 5 y 6 cuerdas**.
- Más de **70 afinaciones predefinidas**, organizadas en dos modos:
  - **Afinaciones comunes**: estándar, medio/un tono arriba o abajo, todos los Drop (D, C#, C, B, Bb, A, Ab…), Open D/E/G/A/C, DADGAD, todo en cuartas/quintas, Nashville, New Standard Tuning, barítono, etc.
  - **Afinaciones de bandas**: afinaciones reales documentadas de bandas como **Sonic Youth, My Bloody Valentine, King Gizzard & the Lizard Wizard, Soundgarden, Alice in Chains, Deftones, Korn, Primus**, entre otras.
- Reproducción de referencia de cada cuerda con **síntesis física (Karplus-Strong vía AudioWorklet)**, que suena a cuerda pulsada real en vez de un tono sintético plano, con respaldo automático a síntesis aditiva si el navegador no soporta AudioWorklet.
- Botón **"Reproducir todas las cuerdas"** para escuchar la afinación completa en secuencia.

#### 🎙️ Configuración de micrófono profesional
- Selector de dispositivo de entrada (útil si tenés interfaz de audio externa).
- Control de **ganancia de entrada** en tiempo real.
- **Sensibilidad / noise gate** ajustable para ignorar ruido de fondo.
- Toggles independientes de **cancelación de eco, supresión de ruido y ganancia automática** (podés desactivarlos para una señal más "cruda" y precisa al afinar o grabar).

#### 🔴 Grabación multipista de alta fidelidad
- **Cuenta regresiva 3-2-1** antes de empezar a grabar, para prepararte.
- **Visualizador tipo espectrograma en vivo**, con barras animadas en gradiente rosa-menta mientras grabás.
- **Pistas independientes**: cada grabación se guarda como "Pista 1", "Pista 2", etc. — podés grabar todas las que quieras sin perder las anteriores.
- **Reproducción individual** de cada pista con un solo clic.
- **Selección de pista** para exportar solo la que te interesa, o **exportar todo** de una vez.
- **Máxima calidad de grabación posible en la web**:
  - El `AudioContext` intenta abrirse a la mayor tasa de muestreo soportada por tu hardware (192 kHz → 96 kHz → 48 kHz).
  - El micrófono se solicita con `sampleRate` y `sampleSize` ideales al máximo.
  - Exportación en **WAV PCM float de 32 bits**, sin cuantizar a enteros de 16 bits — se guarda exactamente la resolución que entrega el motor de audio del navegador (el techo de fidelidad posible sin backend externo).

#### 🌍 Multi-idioma
- Interfaz completa en **español, inglés, portugués y japonés**, con selector de idioma persistente.

#### 💾 Preferencias persistentes
- Instrumento, afinación, modo, referencia A4, idioma y configuración de micrófono se guardan en `localStorage` — al volver a abrir el afinador, todo queda como lo dejaste.

#### 🎀 Diseño
- Interfaz "cute" hecha a mano, con gauge tipo pedal de efectos, tipografías Baloo 2 / Quicksand / Space Mono, y totalmente responsive (funciona bien en celular).

### 🚀 Cómo usarlo

**Opción 1 — Directo desde GitHub Pages (recomendado para quien solo quiere usarlo):**

1. Andá a **Settings → Pages** en este repositorio.
2. En "Branch", elegí `main` (o la rama donde está el HTML) y la carpeta `/root` (o `/docs` si lo movés ahí).
3. Guardá. GitHub te va a dar una URL tipo:
   ```
   https://<tu-usuario>.github.io/<nombre-del-repo>/
   ```
4. Entrá a esa URL desde el navegador (funciona en desktop y celular) y dale permiso al micrófono cuando lo pida.

**Opción 2 — Descargarlo y abrirlo local:**

1. Descargá el archivo `.html` del repositorio (botón **Code → Download ZIP**, o `git clone`).
2. Abrilo haciendo doble clic — se abre en tu navegador por defecto. No necesita servidor ni instalación.

### 🖥️ Compatibilidad

| Navegador | Afinador | Reproducción física (AudioWorklet) | Grabación |
|---|---|---|---|
| Chrome / Edge (desktop y Android) | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ |
| Safari (macOS / iOS) | ✅ | ⚠️ usa respaldo de síntesis aditiva en versiones viejas | ✅ |

Requiere permiso de micrófono del navegador. Recomendado usar auriculares al afinar para evitar que el parlante retroalimente el micrófono.

### 🛠️ Stack técnico

- **HTML + CSS + JavaScript vanilla** — sin frameworks, sin dependencias, sin build step.
- **Web Audio API**: `AnalyserNode`, `ScriptProcessorNode`, `AudioWorklet` (síntesis física Karplus-Strong).
- **MediaDevices / getUserMedia** para captura de micrófono.
- **localStorage** para preferencias.
- Codificación de audio propia (WAV float32) sin librerías externas.

### 🤝 Contribuir

¿Encontraste un bug, querés sumar la afinación de tu banda favorita o un idioma nuevo? ¡Los PRs son bienvenidos!

1. Hacé un fork del repositorio.
2. Creá una rama: `git checkout -b mi-mejora`.
3. Editá el archivo HTML (todo está en un solo archivo, buscá la sección relevante por los comentarios `/* ===== */`).
4. Abrí un Pull Request describiendo el cambio.

---

<br>

## 🇬🇧 English

### What is this?

**Afinador de Matilde** ("Matilde's Tuner") is a chromatic guitar & bass tuner that runs **entirely in the browser**, featuring real-time pitch detection, a huge library of tunings (including real tunings used by actual bands), physically-modeled string playback, and a full **high-fidelity multitrack recording** module. No backend, no install, no build step — it's a single HTML file.

> 🔒 **Privacy first**: all audio processing happens locally in your browser. Your microphone audio is never sent to any server.

### ✨ Features

#### 🎯 Real-time tuner
- Pitch detection using the **YIN algorithm** (autocorrelation) over the Web Audio API `AnalyserNode`, tuned for low notes (6-string bass, drop tunings).
- Effects-pedal-style visual gauge/needle, reading in **cents**, turning green when the note is in tune.
- Large, readable note name with flat/sharp indication relative to the target.
- **Free chromatic mode**: detects any note regardless of the selected tuning — great for tuning outside the built-in presets.
- **Calibratable A4 reference** (438–445 Hz) to match orchestras or personal preference.

#### 🎻 Instruments & tunings
- Supported instruments: **6-string guitar, 7-string guitar, 4/5/6-string bass**.
- Over **70 built-in tunings**, split into two modes:
  - **Common tunings**: standard, half/whole step up or down, every Drop tuning (D, C#, C, B, Bb, A, Ab…), Open D/E/G/A/C, DADGAD, all-fourths/all-fifths, Nashville, New Standard Tuning, baritone, and more.
  - **Band tunings**: real documented tunings used by bands like **Sonic Youth, My Bloody Valentine, King Gizzard & the Lizard Wizard, Soundgarden, Alice in Chains, Deftones, Korn, Primus**, and others.
- Reference playback for each string using **physical modeling synthesis (Karplus-Strong via AudioWorklet)**, sounding like a real plucked string instead of a flat synth tone, with an automatic additive-synthesis fallback if AudioWorklet isn't supported.
- **"Play all strings"** button to hear the full tuning in sequence.

#### 🎙️ Professional microphone settings
- Input device selector (handy if you use an external audio interface).
- Real-time **input gain** control.
- Adjustable **sensitivity / noise gate** to ignore background noise.
- Independent toggles for **echo cancellation, noise suppression, and automatic gain control** (turn them off for a rawer, more accurate signal when tuning or recording).

#### 🔴 High-fidelity multitrack recording
- **3-2-1 countdown** before recording starts, so you're ready.
- **Live spectrogram-style visualizer**, animated pink-to-mint bars while you record.
- **Independent tracks**: every recording is saved as "Track 1", "Track 2", etc. — keep recording as many as you want without losing previous ones.
- **One-click playback** for each individual track.
- **Track selection** to export just the one you need, or **export everything** at once.
- **Maximum recording quality achievable on the web**:
  - The `AudioContext` tries to open at the highest sample rate your hardware supports (192 kHz → 96 kHz → 48 kHz).
  - The microphone is requested with ideal maximum `sampleRate` and `sampleSize`.
  - Export as **32-bit float PCM WAV**, with no quantization down to 16-bit integers — it stores exactly the resolution the browser's audio engine produces (the fidelity ceiling possible without an external backend).

#### 🌍 Multi-language
- Full interface available in **Spanish, English, Portuguese, and Japanese**, with a persistent language switcher.

#### 💾 Persistent preferences
- Instrument, tuning, mode, A4 reference, language, and mic settings are saved to `localStorage` — everything stays exactly as you left it next time you open the tuner.

#### 🎀 Design
- Hand-crafted "cute" UI with an effects-pedal-style gauge, Baloo 2 / Quicksand / Space Mono typography, fully responsive (works great on mobile).

### 🚀 How to use it

**Option 1 — Directly via GitHub Pages (recommended if you just want to use it):**

1. Go to **Settings → Pages** in this repository.
2. Under "Branch", select `main` (or wherever the HTML lives) and the `/root` folder (or `/docs` if you move it there).
3. Save. GitHub will give you a URL like:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```
4. Open that URL in your browser (desktop or mobile) and grant microphone access when prompted.

**Option 2 — Download and open it locally:**

1. Download the `.html` file from the repository (**Code → Download ZIP**, or `git clone`).
2. Double-click it — it opens in your default browser. No server or install required.

### 🖥️ Compatibility

| Browser | Tuner | Physical playback (AudioWorklet) | Recording |
|---|---|---|---|
| Chrome / Edge (desktop & Android) | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ |
| Safari (macOS / iOS) | ✅ | ⚠️ falls back to additive synthesis on older versions | ✅ |

Requires browser microphone permission. Headphones are recommended while tuning to avoid speaker feedback into the mic.

### 🛠️ Tech stack

- **Vanilla HTML + CSS + JavaScript** — no frameworks, no dependencies, no build step.
- **Web Audio API**: `AnalyserNode`, `ScriptProcessorNode`, `AudioWorklet` (Karplus-Strong physical modeling).
- **MediaDevices / getUserMedia** for microphone capture.
- **localStorage** for preferences.
- Custom audio encoding (float32 WAV) with no external libraries.

### 🤝 Contributing

Found a bug, want to add your favorite band's tuning, or a new language? PRs are welcome!

1. Fork the repository.
2. Create a branch: `git checkout -b my-improvement`.
3. Edit the HTML file (everything lives in a single file — look for the relevant `/* ===== */` comment section).
4. Open a Pull Request describing your change.

---

<br>

## 🇧🇷 Português

### O que é isso?

**Afinador de Matilde** é um afinador cromático de violão/guitarra e baixo que roda **totalmente no navegador**, com detecção de afinação em tempo real, uma enorme biblioteca de afinações (incluindo afinações usadas por bandas reais), reprodução de cordas com síntese física e um módulo completo de **gravação multifaixa de alta fidelidade**. Sem backend, sem instalação, sem build: é um único arquivo HTML.

> 🔒 **Privacidade em primeiro lugar**: todo o processamento de áudio acontece localmente no seu navegador. O áudio do microfone nunca é enviado a nenhum servidor.

### ✨ Funcionalidades

#### 🎯 Afinador em tempo real
- Detecção de afinação com o algoritmo **YIN** (autocorrelação) sobre o `AnalyserNode` da Web Audio API, otimizado para notas graves (baixos de 6 cordas, drop tunings).
- Ponteiro/medidor visual estilo pedal de efeitos, com leitura em **centésimos (cents)** que fica verde quando a nota está afinada.
- Nome da nota grande e legível, com indicação de bemol/sustenido em relação ao alvo.
- **Modo cromático livre**: detecta qualquer nota, independentemente da afinação escolhida — ótimo para afinar fora das afinações predefinidas.
- **Referência A4 calibrável** (438–445 Hz) para se adaptar a orquestras ou preferências pessoais.

#### 🎻 Instrumentos e afinações
- Instrumentos suportados: **violão/guitarra de 6 cordas, guitarra de 7 cordas, baixo de 4, 5 e 6 cordas**.
- Mais de **70 afinações predefinidas**, em dois modos:
  - **Afinações comuns**: padrão, meio-tom/tom acima ou abaixo, todos os Drop (D, C#, C, B, Bb, A, Ab…), Open D/E/G/A/C, DADGAD, tudo em quartas/quintas, Nashville, New Standard Tuning, barítono e mais.
  - **Afinações de bandas**: afinações reais documentadas de bandas como **Sonic Youth, My Bloody Valentine, King Gizzard & the Lizard Wizard, Soundgarden, Alice in Chains, Deftones, Korn, Primus**, entre outras.
- Reprodução de referência de cada corda com **síntese física (Karplus-Strong via AudioWorklet)**, soando como uma corda dedilhada de verdade em vez de um tom sintético plano, com fallback automático para síntese aditiva caso o navegador não suporte AudioWorklet.
- Botão **"Reproduzir todas as cordas"** para ouvir a afinação completa em sequência.

#### 🎙️ Configuração profissional de microfone
- Seletor de dispositivo de entrada (útil se você usa uma interface de áudio externa).
- Controle de **ganho de entrada** em tempo real.
- **Sensibilidade / noise gate** ajustável para ignorar ruído de fundo.
- Alternâncias independentes de **cancelamento de eco, supressão de ruído e ganho automático** (desative-as para um sinal mais "cru" e preciso ao afinar ou gravar).

#### 🔴 Gravação multifaixa de alta fidelidade
- **Contagem regressiva 3-2-1** antes de começar a gravar.
- **Visualizador ao vivo estilo espectrograma**, com barras animadas em degradê rosa-menta enquanto você grava.
- **Faixas independentes**: cada gravação é salva como "Faixa 1", "Faixa 2" etc. — grave quantas quiser sem perder as anteriores.
- **Reprodução individual** de cada faixa com um clique.
- **Seleção de faixa** para exportar apenas a que interessa, ou **exportar tudo** de uma vez.
- **Máxima qualidade de gravação possível na web**:
  - O `AudioContext` tenta abrir na maior taxa de amostragem suportada pelo seu hardware (192 kHz → 96 kHz → 48 kHz).
  - O microfone é solicitado com `sampleRate` e `sampleSize` ideais no máximo.
  - Exportação em **WAV PCM float de 32 bits**, sem quantizar para inteiros de 16 bits — salva exatamente a resolução que o motor de áudio do navegador entrega (o teto de fidelidade possível sem um backend externo).

#### 🌍 Multi-idioma
- Interface completa em **espanhol, inglês, português e japonês**, com seletor de idioma persistente.

#### 💾 Preferências persistentes
- Instrumento, afinação, modo, referência A4, idioma e configurações de microfone são salvos no `localStorage` — tudo permanece como você deixou da próxima vez que abrir o afinador.

#### 🎀 Design
- Interface "fofa" feita à mão, com medidor estilo pedal de efeitos, tipografias Baloo 2 / Quicksand / Space Mono, e totalmente responsiva (funciona bem no celular).

### 🚀 Como usar

**Opção 1 — Direto pelo GitHub Pages (recomendado para quem só quer usar):**

1. Vá em **Settings → Pages** neste repositório.
2. Em "Branch", escolha `main` (ou a branch onde está o HTML) e a pasta `/root` (ou `/docs` se você mover o arquivo para lá).
3. Salve. O GitHub vai gerar uma URL parecida com:
   ```
   https://<seu-usuario>.github.io/<nome-do-repo>/
   ```
4. Acesse essa URL pelo navegador (desktop ou celular) e permita o acesso ao microfone quando solicitado.

**Opção 2 — Baixar e abrir localmente:**

1. Baixe o arquivo `.html` do repositório (**Code → Download ZIP**, ou `git clone`).
2. Dê duplo clique nele — abre no seu navegador padrão. Não precisa de servidor nem instalação.

### 🖥️ Compatibilidade

| Navegador | Afinador | Reprodução física (AudioWorklet) | Gravação |
|---|---|---|---|
| Chrome / Edge (desktop e Android) | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ |
| Safari (macOS / iOS) | ✅ | ⚠️ usa fallback de síntese aditiva em versões antigas | ✅ |

Requer permissão de microfone do navegador. Recomenda-se usar fones de ouvido ao afinar para evitar retorno do alto-falante para o microfone.

### 🛠️ Stack técnica

- **HTML + CSS + JavaScript puro** — sem frameworks, sem dependências, sem build step.
- **Web Audio API**: `AnalyserNode`, `ScriptProcessorNode`, `AudioWorklet` (síntese física Karplus-Strong).
- **MediaDevices / getUserMedia** para captura do microfone.
- **localStorage** para preferências.
- Codificação de áudio própria (WAV float32), sem bibliotecas externas.

### 🤝 Contribuindo

Encontrou um bug, quer adicionar a afinação da sua banda favorita ou um novo idioma? PRs são bem-vindos!

1. Faça um fork do repositório.
2. Crie uma branch: `git checkout -b minha-melhoria`.
3. Edite o arquivo HTML (tudo está em um único arquivo — procure a seção relevante pelos comentários `/* ===== */`).
4. Abra um Pull Request descrevendo a mudança.

---

<br>

## 🇯🇵 日本語

### これは何？

**Afinador de Matilde（マチルデのチューナー）** は、**ブラウザだけで完全に動作する**ギター・ベース用クロマチックチューナーです。リアルタイムのピッチ検出、実在バンドが使用したチューニングを含む膨大なチューニングライブラリ、物理モデリングによる弦の再生音、そして高音質な**マルチトラック録音機能**まで備えています。バックエンド不要、インストール不要、ビルド不要 — HTMLファイル1つだけで完結します。

> 🔒 **プライバシー最優先**：音声処理はすべてブラウザ内でローカルに行われます。マイクの音声がサーバーに送信されることはありません。

### ✨ 機能

#### 🎯 リアルタイムチューナー
- Web Audio APIの`AnalyserNode`を用いた**YINアルゴリズム**（自己相関）によるピッチ検出。低音（6弦ベース、ドロップチューニング）にも最適化。
- エフェクトペダル風のビジュアルゲージ／針。**セント単位**で表示し、チューニングが合うと緑色に変化。
- 大きく読みやすい音名表示と、目標音に対するフラット／シャープの表示。
- **フリークロマチックモード**：選択中のチューニングに関係なく、どんな音でも検出。あらかじめ用意されたチューニング以外を使う場合に便利。
- **A4基準を校正可能**（438〜445Hz）。オーケストラや個人の好みに合わせられます。

#### 🎻 対応楽器とチューニング
- 対応楽器：**6弦ギター、7弦ギター、4弦／5弦／6弦ベース**。
- **70種類以上の内蔵チューニング**を2つのモードに分けて収録：
  - **一般的なチューニング**：標準、半音／全音上げ下げ、あらゆるDropチューニング（D、C#、C、B、Bb、A、Ab…）、Open D/E/G/A/C、DADGAD、完全4度／5度積み、ナッシュビル、New Standard Tuning、バリトンなど。
  - **バンドのチューニング**：**Sonic Youth、My Bloody Valentine、King Gizzard & the Lizard Wizard、Soundgarden、Alice in Chains、Deftones、Korn、Primus** など、実在バンドの実際のチューニングを収録。
- 各弦の参照音を**物理モデリング合成（AudioWorkletによるKarplus-Strong）**で再生し、平坦な合成音ではなく本物の弦を弾いたような音を再現。AudioWorklet非対応ブラウザでは加算合成に自動フォールバック。
- **「すべての弦を再生」**ボタンで、チューニング全体を順番に確認できます。

#### 🎙️ プロ仕様のマイク設定
- 入力デバイスの選択（外部オーディオインターフェース使用時に便利）。
- リアルタイムの**入力ゲイン**調整。
- 背景ノイズを無視するための**感度／ノイズゲート**調整。
- **エコーキャンセレーション、ノイズサプレッション、自動ゲイン制御**をそれぞれ個別にオン／オフ可能（チューニングや録音時により生の正確な信号にしたい場合はオフに）。

#### 🔴 高音質マルチトラック録音
- 録音開始前に**3-2-1のカウントダウン**表示。
- 録音中は**ライブスペクトログラム風のビジュアライザー**をピンク〜ミントのグラデーションバーで表示。
- **独立したトラック**：録音するたびに「トラック1」「トラック2」…として保存され、前のトラックを失わずに何度でも録音可能。
- 各トラックを**ワンクリックで再生**。
- **トラックを選択**して必要な1つだけをエクスポート、または**すべて一括エクスポート**。
- **Web上で実現可能な最高の録音品質**：
  - `AudioContext`はハードウェアが対応する最高のサンプリングレートでの起動を試みます（192kHz → 96kHz → 48kHz）。
  - マイクには理想値として最大の`sampleRate`と`sampleSize`をリクエスト。
  - **32ビット浮動小数点PCM WAV**でエクスポートし、16ビット整数への量子化を行いません — ブラウザの音声エンジンが生成する解像度をそのまま保存します（外部バックエンドなしで到達可能な音質の上限）。

#### 🌍 多言語対応
- **スペイン語・英語・ポルトガル語・日本語**の完全なインターフェースを搭載し、言語設定は保持されます。

#### 💾 設定の保存
- 楽器、チューニング、モード、A4基準、言語、マイク設定は`localStorage`に保存され、次回開いたときも同じ状態から使えます。

#### 🎀 デザイン
- エフェクトペダル風のゲージを備えた手作りの「キュート」なUI。Baloo 2／Quicksand／Space Monoフォントを使用し、モバイルにも完全対応したレスポンシブデザイン。

### 🚀 使い方

**方法1 — GitHub Pagesで直接使う（すぐ使いたい人におすすめ）：**

1. このリポジトリの **Settings → Pages** を開きます。
2. 「Branch」で`main`（HTMLがあるブランチ）と`/root`フォルダ（別フォルダに移動した場合は`/docs`）を選択します。
3. 保存すると、次のようなURLが発行されます：
   ```
   https://<あなたのユーザー名>.github.io/<リポジトリ名>/
   ```
4. そのURLをブラウザ（デスクトップでもモバイルでも）で開き、マイクへのアクセスを許可してください。

**方法2 — ダウンロードしてローカルで開く：**

1. リポジトリから`.html`ファイルをダウンロードします（**Code → Download ZIP** または `git clone`）。
2. ダブルクリックするだけで、デフォルトのブラウザで開きます。サーバーもインストールも不要です。

### 🖥️ 対応状況

| ブラウザ | チューナー | 物理モデリング再生（AudioWorklet） | 録音 |
|---|---|---|---|
| Chrome / Edge（デスクトップ・Android） | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ |
| Safari（macOS / iOS） | ✅ | ⚠️ 古いバージョンでは加算合成にフォールバック | ✅ |

ブラウザのマイク許可が必要です。チューニング時はスピーカーの音がマイクに回り込まないよう、ヘッドホンの使用をおすすめします。

### 🛠️ 技術スタック

- **素のHTML + CSS + JavaScript** — フレームワークなし、依存関係なし、ビルド不要。
- **Web Audio API**：`AnalyserNode`、`ScriptProcessorNode`、`AudioWorklet`（Karplus-Strong物理モデリング）。
- マイク取得のための**MediaDevices / getUserMedia**。
- 設定保存のための**localStorage**。
- 外部ライブラリなしの独自音声エンコーディング（float32 WAV）。

### 🤝 コントリビュート

バグを見つけた、好きなバンドのチューニングを追加したい、新しい言語を追加したい — そんな方のPull Requestを歓迎します！

1. リポジトリをフォークします。
2. ブランチを作成：`git checkout -b my-improvement`
3. HTMLファイルを編集します（すべて1つのファイルにまとまっています。`/* ===== */`コメントで該当セクションを探してください）。
4. 変更内容を説明したPull Requestを開いてください。

---

<br>

## 📄 Licencia / License / Licença / ライセンス

Este proyecto se distribuye bajo la licencia **MIT** — sos libre de usarlo, modificarlo y distribuirlo. Si preferís otra licencia, reemplazá esta sección y agregá el archivo `LICENSE` correspondiente.

This project is distributed under the **MIT** license — feel free to use, modify, and distribute it. If you'd prefer a different license, replace this section and add the corresponding `LICENSE` file.

Este projeto é distribuído sob a licença **MIT** — sinta-se livre para usar, modificar e distribuir. Se preferir outra licença, substitua esta seção e adicione o arquivo `LICENSE` correspondente.

このプロジェクトは**MITライセンス**の下で配布されています。自由に使用・改変・配布していただけます。別のライセンスを希望する場合は、このセクションを置き換えて対応する`LICENSE`ファイルを追加してください。

<div align="center">

Hecho con 💗 · Made with 💗 · Feito com 💗 · 💗を込めて

</div>
