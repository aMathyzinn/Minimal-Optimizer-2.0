<!--- README moderno para Minimal Optimizer 2.0 -->

<!-- Badges -->
[![Release](https://img.shields.io/github/v/release/aMathyzin/Minimal-Optimizer-2.0?style=for-the-badge)](https://github.com/aMathyzin/Minimal-Optimizer-2.0/releases)
[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue?style=for-the-badge)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20.NET%208.0-dark?style=for-the-badge)](#requirements)
[![Stars](https://img.shields.io/github/stars/aMathyzin/Minimal-Optimizer-2.0?style=social)](https://github.com/aMathyzin/Minimal-Optimizer-2.0)

# Minimal Optimizer 2.0

Um otimizador leve, seguro e focado em desempenho para Windows — desenvolvido em **C# (.NET 8)** com interface WPF minimalista. Limpe RAM, otimize serviços e recupere fluidez em segundos.

<p align="center">
  <!-- Substitua pelos assets reais: assets/hero.gif ou assets/screenshot.png -->
  <img src="assets/hero.gif" alt="Minimal Optimizer Demo" width="900" style="max-width:100%; border-radius:12px; box-shadow: 0 8px 30px rgba(0,0,0,0.6);">
</p>

> Experimente agora: baixe a última release ou compile localmente. Resultados visíveis em minutos.

---

## Recursos Principais

- ✅ Limpeza inteligente de RAM e cache
- ✅ Otimizações seguras do sistema e serviços do Windows
- ✅ Monitoramento em tempo real de CPU, RAM e Disco
- ✅ Interface minimalista, portátil e sem instalação obrigatória
- ✅ Modo portátil (publicação self-contained disponível)

## Por que usar

Minimal Optimizer foi criado para usuários que querem desempenho real sem complicações: operações com rollback, visual claro do que está sendo mudado e ações que priorizam estabilidade.

## Tecnologias e libs

- C# / .NET 8.0
- WPF (Windows Presentation Foundation)
- System.Management (informações de hardware)
- PerformanceCounters (monitoramento)
- Optional: Newtonsoft.Json (se necessário para export/import de profiles)

## Arquivos sugeridos (imagens / ícones)

Coloque os arquivos abaixo na pasta `assets/` do repositório para o README renderizar bonito:

- `assets/hero.gif` — GIF curto mostrando a interface (3–6s)
- `assets/screenshot.png` — screenshot em alta resolução
- `assets/icons/cpu.svg`, `assets/icons/ram.svg`, `assets/icons/disk.svg` — ícones SVG para features

Exemplo rápido de ícone SVG (copie para `assets/icons/cpu.svg`):

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24" fill="none" stroke="#FF3333" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <rect x="3" y="3" width="18" height="18" rx="2" ry="2"></rect>
  <rect x="7" y="7" width="10" height="10" rx="1" ry="1"></rect>
</svg>
```

---

## Instalação (Windows)

1. Baixe a última release em "Releases". (recomendada para usuários finais)
2. Ou clone o repositório e compile localmente:

```bash
git clone https://github.com/aMathyzin/Minimal-Optimizer-2.0.git
cd Minimal-Optimizer-2.0
dotnet build -c Release
```

Para gerar a versão portátil (self-contained):

```bash
dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true -p:IncludeAllContentForSelfExtract=true
```

Os binários ficarão em `bin/Release/net8.0-windows/publish/`.

---

## Uso Rápido

- Abra o executável `MinimalOptimizer2.exe` como administrador (recomendado).
- Na interface, clique em **Otimizar** para iniciar um run rápido.
- Use o painel de diagnóstico para ver o que foi alterado.

## Automação / CI (GitHub Actions)

Adicionar workflow básico para build e criação de release automatizada:

```yaml
name: .NET Publish

on:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '8.x'
      - name: Build
        run: dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true -p:IncludeAllContentForSelfExtract=true -o publish/
      - name: Upload release artifact
        uses: actions/upload-artifact@v4
        with:
          name: minimal-optimizer-win
          path: publish/
```

---

## Contribuindo

- Abra issues para bugs ou sugestões.
- Faça um fork, crie uma branch e envie PR com pequenas mudanças.
- Mantenha commits atômicos e escreva uma descrição clara do PR.

Sugestões rápidas para PR:

- Adicionar testes automatizados para operações críticas.
- Melhorar mensagens de UI e verificação de permissões.

---

## Segurança

- Operações críticas incluem backup prévio quando aplicável.
- Evite executar sem entender ações listadas no painel de diagnóstico.

---

## Licença

Este projeto é licenciado sob a **GPL-3.0**. Veja o arquivo `LICENSE` para detalhes.

---

- **Baixe a última release**: [Releases](https://github.com/aMathyzin/Minimal-Optimizer-2.0/releases)
- **Experimente agora**: compile localmente e teste o modo portátil
- **Gostou?** Dê uma estrela ⭐ e compartilhe
- **Relatou um bug?** Abra uma issue — respondo rápido.

---

Made with ❤️ by aMathyzin Studio — Performance com elegância.
