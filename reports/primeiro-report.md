
---

# ✅ O que foi feito?

A equipe desenvolveu a base funcional do aplicativo de detecção de sonolência, com foco no processamento de imagens e na lógica de detecção. O que já está implementado:

### ✔️ 1. Arquitetura de processamento da câmera

* Captura de imagem em tempo real usando **CameraX**
* Componentes visuais de sobreposição: `GraphicOverlay`
* Componentes do fluxo da câmera:

  * `CameraXViewModel`
  * `CameraImageGraphic`

### ✔️ 2. Detecção facial e análise de sonolência

Processadores responsáveis pela análise da imagem:

* `FaceDetectorProcessor`
* `FaceDetectorProcessorOriginal.kt`
* `VisionImageProcessor`
* `VisionProcessorBase`

O sistema já detecta rosto, olhos e sinais de sonolência.

### ✔️ 3. Camada utilitária

Classes que dão suporte ao funcionamento do app:

* `BitmapUtils` – manipulação de imagens
* `BluetoothCommander` / `BluetoothDeviceSender` – comunicação Bluetooth
* `FrameMetadata` – metadados dos frames
* `SoundPoolManager` – gerenciamento de sons de alerta

### ✔️ 4. Integração de áudio

Alertas sonoros adicionados em `/res/raw`:

* `beep.mp3`
* `mao.mp3`
* `duvida_vandeco.mp3`

### ✔️ 5. Estrutura geral do app

* `AndroidManifest.xml` configurado
* Layout básico (`activity_main.xml`)
* Ícones do app em múltiplas resoluções
* Configurações Gradle ajustadas

**Resumo:** A parte lógica e técnica da detecção já está funcional.

---

# 🟡 O que falta fazer?

Agora, o foco do projeto é **criar a interface gráfica (UI/UX)** para tornar o app mais intuitivo e visualmente agradável.

### 🔧 1. Interface gráfica

* Redesenhar o layout principal
* Criar botões, ícones e indicadores
* Criar UI clara para:

  * ativar/desativar detecção
  * visualizar alertas
  * verificar conexão Bluetooth
  * mostrar status da detecção

### 🔧 2. Melhorar experiência do usuário

* Adicionar feedback visual sobre níveis de sonolência
* Adicionar animações, cores e indicadores amigáveis

### 🔧 3. Telas adicionais (se necessário)

* Tela de configurações
* Tela de ajuda
* Tela “sobre o aplicativo”

### 🔧 4. Ajustes técnicos finais

* Verificar dependências
* Otimizar desempenho
* Finalizar integração com Bluetooth

### 🔧 5. CI/CD e Docker (opcional, mas recomendado)

* Padronizar ambiente de desenvolvimento
* Evitar erros de dependência
* Facilitar build automático

---

# ❌ Principais dificuldades

O grupo enfrentou vários desafios durante o desenvolvimento:

### ❗ 1. Dificuldade com UI e Front-end

A equipe não tinha experiência com design e construção de interfaces, o que tornou a parte visual mais complexa.

### ❗ 2. Tempo limitado

* Múltiplas tarefas simultaneamente
* Curva de aprendizado alta em Android e visão computacional

### ❗ 3. Planejamento e reuniões

* Dificuldade em alinhar horários
* Atrasos em decisões técnicas

### ❗ 4. Problemas no Android Studio

* Dependências com erro
* Falta de CI/CD e Docker desde o início
* Ambientes diferentes entre membros do grupo

### ❗ 5. Curva de aprendizado da visão computacional

* Entender o pipeline de imagens
* Configurar CameraX + MLKit
* Ajustar performance em tempo real

---

