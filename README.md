# Banana — Releases

Distribuição oficial dos binários do **Banana**, um gestor de notas desktop local-first.

> Este repositório contém só os **builds** e o **changelog**. O código-fonte é mantido em repositório privado; a instalação é pelo Homebrew ou pelos binários abaixo.

---

## 📥 Baixar

Última versão: **[v0.1.5](https://github.com/andre28abr/banana-releases/releases/latest)** (pré-release · **agora multi-plataforma!**)

| Plataforma | Arquivo | Status |
|---|---|---|
| 🍎 **macOS** Apple Silicon (M1/M2/M3/M4) | `Banana_0.1.5_aarch64.dmg` | ✅ Estável |
| 🪟 **Windows** x64 (NSIS installer) | `Banana_0.1.5_x64-setup.exe` | ⚠️ Experimental |
| 🪟 **Windows** x64 (MSI installer) | `Banana_0.1.5_x64_en-US.msi` | ⚠️ Experimental |
| 🐧 **Linux** x64 (Debian/Ubuntu) | `Banana_0.1.5_amd64.deb` | ⚠️ Experimental |
| 🐧 **Linux** x64 (universal AppImage) | `Banana_0.1.5_amd64.AppImage` | ⚠️ Experimental |
| 🐧 **Linux** Flatpak x86_64 (Intel/AMD) | `Banana_0.1.5_x64.flatpak` | ⚠️ Experimental · **autor testou nessa** |
| 🐧 **Linux** Flatpak aarch64 (ARM, ex: VM em Mac Apple Silicon) | `Banana_0.1.5_arm64.flatpak` | ⚠️ Experimental |
| 🍎 **macOS** Intel | — | ⏳ futuro |
| 🐧 **Linux** Flatpak no Flathub | — | ⏳ futuro (depende de aprovação) |

> ⚠️ **Experimental** = build via CI verde mas sem teste manual em Windows/Linux pelo autor. Reporte bugs [aqui](https://github.com/andre28abr/banana-releases/issues).

### Histórico de versões

| Versão | Data | Destaques |
|---|---|---|
| **[v0.1.5](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.5)** | 2026-05-19 | 🐛 **Fix Linux**: nota cripto não volta a mostrar placeholder após unlock · 🔍 **Busca, wikilinks e histórico cripto-aware** (antes não funcionavam em vaults cripto) · ✨ Helper Rust `crypto::decrypt_if_encrypted` · 359 testes (de 338) |
| [v0.1.4](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.4) | 2026-05-19 | 🪟🐧 **Primeira release multi-plataforma** (Win/Linux experimental via CI) · 🔐 AAD versionado (parameter downgrade protection) · 🌐 Encoding auto-detect (UTF-8/16/Windows-1252/MacRoman) · 📁 Code folding · 📜 CRYPTO.md · 338 testes |
| [v0.1.3](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.3) | 2026-05-18 | 🔐 Fase 3 cripto (vault inteiro) · 💬 Comentários inline `{? texto}` estilo Acrobat · 🗃️ Múltiplos cofres + recentes · 🍌 Ícone novo · 🛠️ Qualidade open source (ESLint + Clippy + CI + LICENSE/CONTRIBUTING/SECURITY) · 316 testes (de 111) |
| [v0.1.2](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.2) | 2026-05-17 | 🔐 Notas com senha (Fase 1 do plano de cripto) — AES-256-GCM + Argon2id, design key-slots (LUKS/FileVault style), recovery key obrigatória, formato versionado, 11 testes Rust novos |
| [v0.1.1](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.1) | 2026-05-17 | Auditoria de segurança (DOMPurify + path traversal fixes) · Export PDF vetorial nativo (NSPrintOperation) · Mermaid · Copy as HTML · Histórico de notas · Apresentação · Wikilinks · 70 testes Vitest |
| [v0.1.0](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.0) | 2026-05-15 | Primeira pré-release pública — editor MD 4 modos, 70+ linguagens de código, viewer PDF, 8 temas, modo Projeto |

---

## 🍎 Instalação no macOS

### Via Homebrew (recomendado)

```bash
brew tap andre28abr/banana
brew trust andre28abr/banana
brew install --cask banana
```

Depois é só abrir pelo Spotlight ou `open -a Banana`. Atualizar depois:

```bash
brew upgrade --cask banana
```

Homebrew já limpa a flag de quarantine automaticamente — não precisa do clique-direito → Abrir da primeira vez.

Detalhes e alternativas no [tap oficial](https://github.com/andre28abr/homebrew-banana).

> **Requisitos**: Apple Silicon (M1/M2/M3/M4) + macOS Ventura (13) ou superior. Intel Mac ainda não suportado.

### Manual (Apple Silicon ou Intel via download direto)

1. Baixe o `.dmg` da [última release](https://github.com/andre28abr/banana-releases/releases/latest)
2. Abra o DMG e arraste **Banana** para a pasta **Aplicativos**
3. Na **primeira vez**, abra com **clique direito → Abrir**

> **Por que esse passo extra?** O Banana ainda não é assinado pela Apple ($99/ano de Developer ID). Sem assinatura, o macOS bloqueia abertura por padrão. Com clique direito → Abrir, você confirma uma vez e nunca mais precisa fazer.
>
> **Alternativa via Terminal:**
> ```bash
> xattr -d com.apple.quarantine /Applications/Banana.app
> ```

A partir da segunda abertura, duplo clique funciona normalmente.

---

## 🪟 Instalação no Windows

1. Baixe `Banana_0.1.5_x64-setup.exe` (NSIS — recomendado, mais leve) ou `Banana_0.1.5_x64_en-US.msi`
2. Execute o instalador
3. SmartScreen do Windows Defender vai avisar → clique em **"Mais informações"** → **"Executar mesmo assim"**

> O app ainda não é assinado pela Microsoft (Authenticode certificate custa ~$200/ano).
> Esse aviso some quando o autor obter o certificado.

---

## 🐧 Instalação no Linux

### Debian/Ubuntu (.deb)
```bash
sudo dpkg -i Banana_0.1.5_amd64.deb
# Se reclamar de deps faltando:
sudo apt-get install -f
```

### Qualquer distro (.AppImage)
```bash
chmod +x Banana_0.1.5_amd64.AppImage
./Banana_0.1.5_amd64.AppImage
```

### Flatpak (single-file, qualquer distro com Flatpak instalado)

Escolha o flatpak da arquitetura da sua máquina/VM. Pra descobrir, rode:
```bash
uname -m
```

- **`x86_64`** (Intel/AMD comum) → use `Banana_0.1.5_x64.flatpak`
- **`aarch64`** ou `arm64` (ARM — ex: VMs Linux em Mac Apple Silicon via UTM/Parallels/VMware Fusion) → use `Banana_0.1.5_arm64.flatpak`

```bash
# Adicionar Flathub (uma vez só) — precisa do runtime base
flatpak remote-add --user --if-not-exists flathub \
  https://flathub.org/repo/flathub.flatpakrepo

# Instalar (substitua _x64 por _arm64 se for ARM)
flatpak install --user Banana_0.1.5_x64.flatpak

# Rodar
flatpak run dev.banana.Banana
```

> Flatpak é o formato preferível pra distros recentes (Fedora, Ubuntu 22+, Arch, etc) —
> isola o app em sandbox e atualiza sem mexer no sistema.

---

## 🍌 Vaults de exemplo

Pra explorar o app sem criar nada do zero, baixe um dos vaults de demonstração:

| Arquivo | O que tem |
|---|---|
| [`vault-plain.zip`](https://github.com/andre28abr/banana-releases/releases/download/v0.1.5/vault-plain.zip) (21 KB) | 17 notas sem cripto — markdown completo, mermaid, KaTeX, código em 6 linguagens, ABNT |
| [`vault-encrypted.zip`](https://github.com/andre28abr/banana-releases/releases/download/v0.1.5/vault-encrypted.zip) (54 KB) | Mesmas notas, todas criptografadas (AES-256-GCM + Argon2id) |

**Senha do vault encriptado:** `banana-demo`

Como usar:
1. Descompacte o `.zip` numa pasta qualquer
2. No Banana: **Arquivo → Abrir Cofre…** e selecione a pasta
3. (Encrypted) Ao clicar numa nota, digite `banana-demo`

> A senha é pública de propósito — é demo. Use senha forte pra notas reais.

---

## 🐛 Reportar bugs

Por enquanto, contate o autor diretamente. Quando o repositório de código-fonte virar público (planejado pra v0.5+), as issues abrem lá.

---

## 📜 Licença

Por enquanto, **MIT** (sob revisão). Veja `LICENSE` em cada release.

---

## 👤 Autor

**André Augusto Azarias de Souza** · DPO / Encarregado de Dados · Compliance & GRC · Privacy Engineering

Gestor com **18 anos de atuação como Gerente Administrativo e Encarregado de Dados (DPO)** em organização do setor de saúde suplementar, ambiente regulado pela ANS e pela LGPD. Desde 2025 conduz, como **product owner técnico**, projetos open-source de segurança e privacidade em Python, Go, Rust e Swift, com a codificação orquestrada por assistentes de IA generativa sob sua direção e revisão. O banana leva o princípio de minimização de dados para o bloco de notas: local-first, sem conta, sem servidor, com vault cifrado.

Outros projetos: [SentinelBR](https://github.com/andre28abr/SentinelBR-platform) · [VigiaOS](https://github.com/andre28abr/VigiaOS) · [Plataforma LGPD](https://github.com/andre28abr/lgpd-platform) · [Peapod](https://github.com/andre28abr/Peapod) · [Uptend](https://github.com/andre28abr/Uptend)

→ [LinkedIn](https://linkedin.com/in/andreaugusto-azariasdesouza) · [Perfil no GitHub](https://github.com/andre28abr)
