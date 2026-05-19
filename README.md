# Banana — Releases

Distribuição oficial dos binários do **Banana**, um gestor de notas desktop local-first.

> Esse repositório só contém **builds** e **changelog**. O código-fonte vive em outro repositório (privado por enquanto, vai virar público quando estabilizar).

---

## 📥 Baixar

Última versão: **[v0.1.4](https://github.com/andre28abr/banana-releases/releases/latest)** (pré-release · **agora multi-plataforma!**)

| Plataforma | Arquivo | Status |
|---|---|---|
| 🍎 **macOS** Apple Silicon (M1/M2/M3/M4) | `Banana_0.1.4_aarch64.dmg` | ✅ Estável |
| 🪟 **Windows** x64 (NSIS installer) | `Banana_0.1.4_x64-setup.exe` | ⚠️ Experimental |
| 🪟 **Windows** x64 (MSI installer) | `Banana_0.1.4_x64_en-US.msi` | ⚠️ Experimental |
| 🐧 **Linux** x64 (Debian/Ubuntu) | `Banana_0.1.4_amd64.deb` | ⚠️ Experimental |
| 🐧 **Linux** x64 (universal AppImage) | `Banana_0.1.4_amd64.AppImage` | ⚠️ Experimental |
| 🐧 **Linux** Flatpak (single-file) | `Banana_0.1.4_x64.flatpak` | ⚠️ Experimental |
| 🍎 **macOS** Intel | — | ⏳ futuro |
| 🐧 **Linux** Flatpak no Flathub | — | ⏳ futuro (depende de aprovação) |

> ⚠️ **Experimental** = build via CI verde mas sem teste manual em Windows/Linux pelo autor. Reporte bugs [aqui](https://github.com/andre28abr/banana/issues).

### Histórico de versões

| Versão | Data | Destaques |
|---|---|---|
| **[v0.1.4](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.4)** | 2026-05-19 | 🪟🐧 **Primeira release multi-plataforma** (Win/Linux experimental via CI) · 🔐 AAD versionado (parameter downgrade protection) · 🌐 Encoding auto-detect (UTF-8/16/Windows-1252/MacRoman) · 📁 Code folding · 📜 CRYPTO.md · 338 testes |
| [v0.1.3](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.3) | 2026-05-18 | 🔐 Fase 3 cripto (vault inteiro) · 💬 Comentários inline `{? texto}` estilo Acrobat · 🗃️ Múltiplos cofres + recentes · 🍌 Ícone novo · 🛠️ Qualidade open source (ESLint + Clippy + CI + LICENSE/CONTRIBUTING/SECURITY) · 316 testes (de 111) |
| [v0.1.2](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.2) | 2026-05-17 | 🔐 Notas com senha (Fase 1 do plano de cripto) — AES-256-GCM + Argon2id, design key-slots (LUKS/FileVault style), recovery key obrigatória, formato versionado, 11 testes Rust novos |
| [v0.1.1](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.1) | 2026-05-17 | Auditoria de segurança (DOMPurify + path traversal fixes) · Export PDF vetorial nativo (NSPrintOperation) · Mermaid · Copy as HTML · Histórico de notas · Apresentação · Wikilinks · 70 testes Vitest |
| [v0.1.0](https://github.com/andre28abr/banana-releases/releases/tag/v0.1.0) | 2026-05-15 | Primeira pré-release pública — editor MD 4 modos, 70+ linguagens de código, viewer PDF, 8 temas, modo Projeto |

---

## 🍎 Instalação no macOS

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

1. Baixe `Banana_0.1.4_x64-setup.exe` (NSIS — recomendado, mais leve) ou `Banana_0.1.4_x64_en-US.msi`
2. Execute o instalador
3. SmartScreen do Windows Defender vai avisar → clique em **"Mais informações"** → **"Executar mesmo assim"**

> O app ainda não é assinado pela Microsoft (Authenticode certificate custa ~$200/ano).
> Esse aviso some quando o autor obter o certificado.

---

## 🐧 Instalação no Linux

### Debian/Ubuntu (.deb)
```bash
sudo dpkg -i Banana_0.1.4_amd64.deb
# Se reclamar de deps faltando:
sudo apt-get install -f
```

### Qualquer distro (.AppImage)
```bash
chmod +x Banana_0.1.4_amd64.AppImage
./Banana_0.1.4_amd64.AppImage
```

### Flatpak (single-file, qualquer distro com Flatpak instalado)
```bash
flatpak install --user Banana_0.1.4_x64.flatpak
flatpak run dev.banana.Banana
```

> Flatpak é o formato preferível pra distros recentes (Fedora, Ubuntu 22+, Arch, etc) —
> isola o app em sandbox e atualiza sem mexer no sistema.

---

## 🐛 Reportar bugs

Por enquanto, contate o autor diretamente. Quando o repositório de código-fonte virar público (planejado pra v0.5+), as issues abrem lá.

---

## 📜 Licença

Por enquanto, **MIT** (sob revisão). Veja `LICENSE` em cada release.

---

## 👤 Autor

**André Augusto Azarias De Souza** — [github.com/andre28abr](https://github.com/andre28abr)

DPO / especialista em compliance e privacidade em transição pra desenvolvimento. O Banana é o segundo projeto público — o primeiro é [SentinelBR](https://github.com/andre28abr) (também em desenvolvimento).
