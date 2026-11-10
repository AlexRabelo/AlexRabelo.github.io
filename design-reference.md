# Referências de design — Portfólio Alex Rabelo

Documento de consulta para agentes e para o autor. Consolida os sistemas de design que inspiram este portfólio, com as adaptações aplicadas ao nosso contexto.

**Regra de leitura:** as seções "Herdado" descrevem o que foi adotado. As seções "Descartado" descrevem o que foi deliberadamente rejeitado. Nunca importe algo de "Descartado" sem pedido explícito.

---

## 1. Resend — estrutura e botões

**Origem:** https://styles.refero.design/style/0d914ef0-fa84-4c60-a9aa-cef0b5eb6e5d
**Arquétipo:** black velvet with violet neon
**Tema:** dark

### O que o Resend faz

Fundo preto absoluto (`#000000`), bordas hairline `#292d30`, tipografia branca sobre preto. A mono (Commit Mono) carrega toda a identidade de desenvolvedor — blocos de código, badges, labels inline. O violeta aparece só em identificadores de código, como syntax highlighting, nunca em botões.

Botões são sempre ghost: fundo transparente, borda 1px, texto claro. Nunca botão preenchido colorido como CTA principal.

### Herdado para o nosso sistema

**Botões ghost como padrão único.**
```css
.btn {
  display: inline-flex;
  align-items: center;
  gap: var(--sp-1);
  padding: var(--sp-1) var(--sp-2);
  border: 1px solid var(--border);
  border-radius: var(--r-sm);
  color: var(--text);
  background: transparent;
  font-family: var(--font-mono);
  font-size: var(--fs-sm);
  transition: border-color 0.15s ease, color 0.15s ease;
}
.btn:hover, .btn:focus-visible {
  border-color: var(--accent);
  color: var(--accent);
}