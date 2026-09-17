# Prompt para usar no Codex do VS Code

Abra a pasta deste projeto no VS Code e cole a mensagem abaixo no Codex:

> Este é o projeto completo da minha loja ATELIÊ 01. Preserve o visual e as funcionalidades existentes. Primeiro leia README.md, src/App.tsx, src/styles.css, firestore.rules e .env.example. Execute a instalação, verifique o build e me ajude a ligar meu projeto Firebase sem colocar dados sensíveis no código ou no Git. Configure Authentication por e-mail/senha para o proprietário, leitura pública do documento Firestore site/main e gravação somente pelo UID administrador, com as regras correspondentes. Revise o fluxo de edição do painel Desenvolvedor, catálogo, sacola, tamanhos e mensagem de checkout no WhatsApp. Faça os ajustes necessários, valide no navegador em desktop e celular, e use os valores públicos já presentes em .env.local e me diga como obter o UID do administrador e quais passos devo fazer manualmente no console. Não invente credenciais, número do WhatsApp, produtos nem preços reais. Depois de configurado e testado, prepare o deploy no Netlify usando netlify.toml e as variáveis VITE_*.

## Dados que precisarei informar

- Nome definitivo da loja e número do WhatsApp comercial.
- Configuração Web do Firebase: `apiKey`, `authDomain`, `projectId`, `appId`.
- UID da minha conta de administrador no Authentication.
- Produtos reais: fotos, nomes, categorias, tamanhos e preços.

Cole a configuração Web apenas em `.env.local` na sua máquina ou nas variáveis de ambiente do Netlify. Não envie sua senha ou chave privada.
