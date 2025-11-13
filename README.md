# Projeto de Desenvolvimento de Aplicação Móvel para Detecção de Sonolência em Motoristas

Este projeto tem como objetivo o desenvolvimento de um aplicativo Android capaz de detectar sinais de fadiga e sonolência em motoristas em tempo real, utilizando técnicas de visão computacional.

---

## 📂 Estrutura da Documentação

O repositório possui a seguinte organização de documentação:

```bash
.
├── documentation/
│   ├── 1. Descrição do Projeto.md
│   ├── 2. Escopo.md
│   └── 3. Diagramas UML.md
├── LICENSE
└── README.md
```


- **1. Descrição do Projeto.md**: Contém informações gerais sobre o projeto, produto, objetivos, motivação, equipe de desenvolvimento e usuários finais.
- **2. Escopo.md**: Detalha os requisitos funcionais, não funcionais e regras de negócio, incluindo o escopo atual e futuro.
- **3. Diagramas UML.md**: Contém diagramas UML que representam casos de uso, classes e outros aspectos do sistema.

---

## ⚙ Funcionalidades Principais

- Captura contínua de imagens usando a câmera frontal do dispositivo.
- Detecção e análise de rostos e olhos em tempo real.
- Classificação automática do estado dos olhos (abertos ou fechados).
- Contagem de quadros consecutivos com olhos fechados e emissão de alertas sonoros.
- Exibição de indicadores de desempenho, como FPS e latência.

---

## 👥 Equipe de Desenvolvimento

- Gabriela Rodrigues Nascimento
- Gregory Gabriel Ozaki Coelho  
- Leano Guerreiro Baba  
- Taíza Paula de Oliveira Lima  

---

## 📌 Tecnologias Utilizadas

- **Plataforma**: Android  
- **Linguagem**: Kotlin / Java  
- **Bibliotecas de Visão Computacional**: ML Kit  
- **Interface**: Jetpack Compose

---

## Link do Código do Repositório
[Realtime Drawsiness And Yawning Detector](https://github.com/leanoguerreiro/realtime-drawsiness_and_yawning_detector)

O repositório possui a seguinte organização de documentação:

```bash
app/
│
├── manifests/
│   └── AndroidManifest.xml
│
├── kotlin+java/
│   └── io.github.chayanforyou.drowsinessdetection/
│       ├── executors/
│       │   └── ScopedExecutor
│       │
│       ├── overlay/
│       │   └── GraphicOverlay
│       │
│       ├── processors/
│       │   ├── FaceDetectorProcessor
│       │   ├── FaceDetectorProcessorOriginal.kt
│       │   ├── VisionImageProcessor
│       │   └── VisionProcessorBase
│       │
│       ├── utils/
│       │   ├── BitmapUtils
│       │   ├── BluetoothCommander
│       │   ├── BluetoothDeviceSender
│       │   ├── FrameMetadata
│       │   └── SoundPoolManager
│       │
│       └── viewmodels/
│           ├── CameraXViewModel
│           ├── CameralImageGraphic
│           ├── FaceGraphic
│           ├── InferenceInfoGraphic
│           └── MainActivity
│
├── io.github.chayanforyou.drowsinessdetection (androidTest)/
│   └── ExampleInstrumentedTest
│
├── io.github.chayanforyou.drowsinessdetection (test)/
│   └── ExampleUnitTest
│
├── res/
│   ├── layout/
│   │   └── activity_main.xml
│   │
│   ├── mipmap/
│   │   ├── ic_launcher/
│   │   │   ├── ic_launcher.webp (hdpi)
│   │   │   ├── ic_launcher.webp (mdpi)
│   │   │   ├── ic_launcher.webp (xhdpi)
│   │   │   ├── ic_launcher.webp (xxhdpi)
│   │   │   └── ic_launcher.webp (xxxhdpi)
│   │   │
│   │   └── ic_launcher_round/
│   │       ├── ic_launcher_round.webp (hdpi)
│   │       ├── ic_launcher_round.webp (mdpi)
│   │       ├── ic_launcher_round.webp (xhdpi)
│   │       ├── ic_launcher_round.webp (xxhdpi)
│       │       └── ic_launcher_round.webp (xxxhdpi)
│   │
│   ├── raw/
│   │   ├── beep.mp3
│   │   ├── duvida_vandeco.mp3
│   │   └── mao.mp3
│   │
│   └── values/
│       ├── colors.xml
│       ├── strings.xml
│       └── themes.xml
│
├── res (generated)/
│
└── Gradle Scripts/
    ├── build.gradle.kts (Project: Drowsiness_Detection)
    ├── build.gradle.kts (Module: app)
    ├── proguard-rules.pro
    ├── gradle.properties
    ├── gradle-wrapper.properties
    ├── libs.versions.toml
    ├── local.properties
    └── settings.gradle.kts
```
