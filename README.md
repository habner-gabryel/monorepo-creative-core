# monorepo-creative-core

Mono repositório contendo projetos desenvolvidos durante o **Creative Core Pathway** do Unity Learn. Cada pasta representa um projeto independente com foco em diferentes aspectos do desenvolvimento criativo no Unity (animação, iluminação, shaders, renderização arquitetônica).

---

## 📁 Estrutura do Repositório

```
monorepo-creative-core/
├── CreativeCore_Animation/          # Projeto de Animação
├── Lighting/                        # Projeto de Iluminação (versão principal)
├── Introduction-Creative-Core/      # Projeto Introdutório - Renderização Arquitetônica
├── rtl-creativecore-shaders/        # Projeto de Shaders (Shader Graph)
├── creativecore-lighting/           # Projeto de Iluminação (versão 2022.3 LTS)
├── Challenge Ligthing - v2/         # Desafio de Iluminação v2
└── Challeng Lighting - v3/          # Desafio de Iluminação v3
```

> **Nota:** Todos os projetos utilizam **Unity 2022.3 LTS** (exceto `rtl-creativecore-shaders` que usa 2022.3.36f1) e **Universal Render Pipeline (URP)**.

---

## 🎬 1. CreativeCore_Animation

**Pasta:** `CreativeCore_Animation/`  
**Unity Version:** 2022.3.59f1  
**Render Pipeline:** URP

### Descrição
Projeto focado em **sistemas de animação** no Unity, cobrindo desde animações básicas até controllers complexos, blend trees, e integração com sistemas de gameplay.

### Principais Funcionalidades

| Sistema | Descrição |
|---------|-----------|
| **Animator Controllers** | Controllers para porta, animações compartilhadas, third-person |
| **Blend Trees** | Transições suaves entre animações (idle, walk, run) |
| **Animation Events** | Eventos de passos (footsteps) sincronizados com áudio |
| **Triggers/Parameters** | Controle via script (abrir porta, dançar, seleção de idle) |

### Scripts Principais (`Assets/CreativeCore_Animation/Scripts/`)

| Script | Responsabilidade |
|--------|------------------|
| `AnimatorControllerTriggers.cs` | Gerencia triggers do animator (porta, dança) |
| `DanceParty.cs` | Sistema de festa de dança com múltiplos personagens |
| `DoorTrigger.cs` | Detecção de proximidade para abrir/fechar porta |
| `FootstepManager.cs` | Gerencia sons de passos baseados no terreno (terra, água, caverna) |
| `IdleAnimSelection.cs` | Seleção aleatória de animações de idle |
| `SimpleCameraController.cs` | Controle de câmera orbital simples |

### Cenas (`Assets/CreativeCore_Animation/Scenes/`)
- `TutorialScene_Animation_Door` — Tutorial de animação de porta
- `TutorialScene_Animation_Outdoor` — Animações em ambiente externo
- `TutorialScene_Animation_SharedAnimation` — Animações compartilhadas entre objetos
- `AnimationScene_Door` — Cena completa com porta animada
- `Animation_SharedAnimation_Scene` — Cena demonstrando shared animations
- `ChallengeScene_Animation` — Cena de desafio final

### Assets Notáveis
- **Starter Assets** — Input System, Third Person Controller
- **Audio** — Passos (terra, água, caverna), água ambiente, música clássica
- **VFX** — Efeitos visuais para animações
- **Animations** — Bounce, Pulse, Distance variations

---

## 💡 2. Lighting (Projeto Principal)

**Pasta:** `Lighting/`  
**Unity Version:** 2022.3.59f1  
**Render Pipeline:** URP

### Descrição
Projeto abrangente de **iluminação** cobrindo ambientes internos, externos e de estúdio. Ensina baking de lightmaps, probes, reflection probes, e configurações de iluminação para URP.

### Cenas (`Assets/CreativeCore_Lighting/Scenes/`)

| Cena | Tipo | Foco |
|------|------|------|
| `TutorialScene_Lighting_Indoor` | Tutorial | Iluminação interna, baked GI |
| `TutorialScene_Lighting_Outdoor` | Tutorial | Iluminação externa, sun, sky |
| `FinalScene_Lighting_Indoor` | Final | Interior completo com lightmaps |
| `FinalScene_Lighting_Outdoor` | Final | Externo com iluminação dinâmica |
| `FinalScene_Lighting_Studio` | Final | Estúdio/renderização de produto |

### Scripts (`Assets/CreativeCore_Lighting/Scripts/`)
- `BouncingObject.cs` — Objeto que quica (demo de iluminação dinâmica)
- `SimpleCameraController.cs` — Navegação nas cenas

### Configurações (`Assets/CreativeCore_Lighting/Settings/`)
- `LightmapParameters.giparams` — Parâmetros de lightmap personalizados
- `Baked Lighting.lighting` — Configuração de baked lighting
- `ProtoLightingSettings.lighting` — Configurações de prototipagem

---

## 🏗️ 3. Introduction-Creative-Core (Renderização Arquitetônica)

**Pasta:** `Introduction-Creative-Core/`  
**Unity Version:** 2022.3.59f1  
**Render Pipeline:** URP

### Descrição
Projeto introdutório do pathway focado em **visualização arquitetônica** — materiais PBR, iluminação realista, UI, shaders customizados (Shader Graph), e pós-processamento.

### Estrutura Principal

#### `Assets/GuidedProject/ArchitecturalRendering/` — Projeto Principal
| Pasta | Conteúdo |
|-------|----------|
| `Models/` | Modelos arquitetônicos (prédios, móveis, decoração) |
| `Materials/` | Materiais PBR realistas (madeira, concreto, vidro, metal) |
| `Textures/` | Texturas albedo, normal, roughness, metallic |
| `Prefabs/` | Prefabs montados (salas, móveis, iluminação) |
| `UI/` | Interface do usuário para walkthrough |
| `Font/` | Fontes (Bebas Neue) |

#### `Assets/GuidedProject/Shared/` — Recursos Compartilhados
| Pasta | Conteúdo |
|-------|----------|
| `Shaders/` | **SimpleCelShader.ShaderGraph** — Shader toon/cel shading |
| `VisualEffectAssets/` | VFX Graph assets |
| `Skies/` | Skyboxes HDR para iluminação |
| `Audio/` | Música ambiente (6 tracks) + SFX (botões, fogo, ondas, ambiência) |
| `UI/Fonts/` | Múltiplas fontes (Alfa Slab, Anton, Felipa, Fjalla One, PT Sans) |
| `Animator/` | `SimpleIdleController.controller` |
| `UniversalRenderPipelineSettings/` | Configurações URP otimizadas |

### Cena Principal
- `Assets/Scenes/ArchitectureScene.unity` — Cena completa de visualização arquitetônica

---

## 🎨 4. rtl-creativecore-shaders

**Pasta:** `rtl-creativecore-shaders/`  
**Unity Version:** 2022.3.36f1  
**Render Pipeline:** URP

### Descrição
Projeto dedicado a **Shader Graph** — criação de shaders visuais sem código. Foca em efeitos avançados como dissolve, shimmer, e shaders modulares para gallery assets.

### Shader Graphs (`Assets/CreativeCore_Shaders/ShaderGraphs/`)

| Shader Graph | Descrição | Material Associado |
|--------------|-----------|-------------------|
| `Example_Dissolve.shadergraph` | Efeito de dissolução com noise/threshold | `Dissolve.mat` |
| `Example_Shimmer.shadergraph` | Efeito brilhante/ondulante (shimmer) | — |
| `Shimmer_ShaderGraph.shadergraph` | Variação avançada do shimmer | `Shimmer.mat` |

### Cenas (`Assets/CreativeCore_Shaders/Scenes/`)
- `TutorialScene_Shaders` — Tutorial passo a passo dos shaders
- `FinalScene_Shaders` — Cena final demonstrando todos os efeitos
- `Modular Gallery Assets.unity` — Gallery de assets modulares com shaders aplicados

### Outros Assets
- `Models/` — Modelos para teste de shaders
- `Textures/` — Texturas de noise, gradient, masks para shaders
- `Materials/` — Materiais pré-configurados
- `Prefabs/` — Prefabs com shaders aplicados

---

## 🔆 5. creativecore-lighting (Versão 2022.3 LTS)

**Pasta:** `creativecore-lighting/creativecore-lighting-2022.3LTS/`  
**Unity Version:** 2022.3.0f1  
**Render Pipeline:** URP

### Descrição
Versão anterior do projeto de iluminação, compatível com **Unity 2022.3.0f1** (versão base LTS). Mesma estrutura do projeto `Lighting/` mas em versão inicial do LTS.

### Estrutura Idêntica a `Lighting/`
- Mesmas cenas (Indoor, Outdoor, Studio — tutorial e final)
- Mesmos scripts (`BouncingObject.cs`, `SimpleCameraController.cs`)
- Mesmas configurações de lighting (`LightmapParameters`, `ProtoLightingSettings`)

> **Uso:** Referência histórica ou compatibilidade com Unity 2022.3.0f1 exato.

---

## 🌲 6. Challenge Ligthing - v2

**Pasta:** `Challenge Ligthing - v2/`  
**Unity Version:** 2022.3.59f1  
**Render Pipeline:** URP

### Descrição
Desafio prático de iluminação v2 usando o **Simple Nature Pack** (assets de natureza low-poly).

### Estrutura
- `Assets/Scenes/SampleScene.unity` — Cena do desafio
- `Assets/SimpleNaturePack/` — Assets de natureza (árvores, rochas, terreno, shaders)

### Foco do Desafio
- Iluminação de ambiente natural/externo
- Baked vs Realtime GI em vegetação
- Light probes para objetos móveis na natureza
- Otimização de lightmaps para folhagem

---

## 🏠 7. Challeng Lighting - v3

**Pasta:** `Challeng Lighting - v3/`  
**Unity Version:** 2022.3.59f1  
**Render Pipeline:** URP

### Descrição
Desafio de iluminação v3 focado em **interior estilizado** — "Stylized Retro Room".

### Estrutura
- `Assets/Scenes/SampleScene.unity` — Cena do desafio (quarto retro)
- `Assets/Stylized Retro Room/` — Assets do quarto (móveis, decoração, texturas stylized)
- `Assets/Settings/` — Configurações de iluminação específicas
- `Assets/TutorialInfo/` — Informações do tutorial/layout

### Foco do Desafio
- Iluminação interna stylized/non-photorealistic
- Color grading e mood lighting
- Emissive materials para neon/LED
- Post-processing para estilo artístico

---

## 🛠️ Tecnologias Comuns

| Tecnologia | Versão/Uso |
|------------|------------|
| **Unity** | 2022.3 LTS (todas as versões) |
| **Render Pipeline** | Universal Render Pipeline (URP) |
| **Input System** | Novo Input System (Starter Assets) |
| **Animation** | Animator Controllers, Blend Trees, Animation Events |
| **Shaders** | Shader Graph (visual), URP Lit/Unlit |
| **Lighting** | Baked GI, Realtime GI, Light Probes, Reflection Probes |
| **Audio** | Audio Sources, Spatial Blend, Animation Events para footsteps |
| **UI** | TextMeshPro, Canvas, Fontes customizadas |
| **VFX** | VFX Graph (Introduction-Creative-Core, rtl-creativecore-shaders) |

---

## 🚀 Como Abrir os Projetos

1. **Unity Hub** → **Add** → Selecione a pasta do projeto desejado
2. Unity detectará a versão (2022.3.x) e solicitará instalação se necessário
3. Abra o projeto — URP já configurado em todos

> **Dica:** Projetos são independentes. Abra apenas o que precisar.

---

## 📚 Progressão de Aprendizado (Origem)

Estes projetos seguem a ordem do **Creative Core Pathway**:

1. **Introduction-Creative-Core** — Fundamentos (renderização arquitetônica)
2. **CreativeCore_Animation** — Sistemas de animação
3. **Lighting** / **creativecore-lighting** — Iluminação completa
4. **rtl-creativecore-shaders** — Shader Graph avançado
5. **Challenge Ligthing - v2** — Desafio: natureza
6. **Challeng Lighting - v3** — Desafio: interior stylized

---

## 📄 Licença

Projetos educacionais baseados no **Unity Learn Creative Core Pathway**. Assets de terceiros (Starter Assets, Simple Nature Pack, Stylized Retro Room) mantêm suas licenças originais.

---

*Última atualização: 2026-10-29*
