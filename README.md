# Banana — Releases

Distribuição oficial dos binários do **Banana**, um gestor de notas desktop local-first.

> Esse repositório só contém **builds** e **changelog**. O código-fonte vive em outro repositório (privado por enquanto, vai virar público quando estabilizar).

---

## 📥 Baixar

Última versão: **[v0.1.0](https://github.com/andre28abr/banana-releases/releases/latest)** (pré-release)

| Plataforma | Arquivo | Status |
|---|---|---|
| 🍎 **macOS** Apple Silicon (M1/M2/M3/M4) | `Banana_x.y.z_aarch64.dmg` | ✅ disponível |
| 🍎 **macOS** Intel | `Banana_x.y.z_x64.dmg` | ⏳ futuro |
| 🐧 **Linux** Flatpak (Flathub) | — | ⏳ futuro |
| 🐧 **Linux** AppImage | `Banana_x.y.z.AppImage` | ⏳ futuro |
| 🪟 **Windows** | `Banana_x.y.z.exe` | ⏳ futuro |

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

## 🐛 Reportar bugs

Por enquanto, contate o autor diretamente. Quando o repositório de código-fonte virar público (planejado pra v0.5+), as issues abrem lá.

---

## 📜 Licença

Por enquanto, **MIT** (sob revisão). Veja `LICENSE` em cada release.

---

## 👤 Autor

**André Augusto Azarias De Souza** — [github.com/andre28abr](https://github.com/andre28abr)

DPO / especialista em compliance e privacidade em transição pra desenvolvimento. O Banana é o segundo projeto público — o primeiro é [SentinelBR](https://github.com/andre28abr) (também em desenvolvimento).
