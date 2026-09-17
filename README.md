# ATELIÊ 01 — loja de roupas

Projeto React 19 + Vite + TypeScript, preparado para Firebase Authentication e Firestore. Vitrine responsiva com busca, categorias, detalhes, tamanhos, sacola e pedido formatado para WhatsApp. O painel **Desenvolvedor** edita textos, cores, imagens, categorias, produtos e contato.

## Abrir no VS Code

1. Extraia este ZIP e abra a pasta `lojaconf` no VS Code.
2. No terminal da pasta, execute `npm install` e depois `npm run dev`.
3. Abra o endereço exibido no terminal. `npm run build` verifica a versão de produção.

## Ativar Firebase

1. Crie um projeto no [Firebase Console](https://console.firebase.google.com/). Registre um **aplicativo Web**, ative **Authentication > E-mail/senha** e crie um **Firestore Database**.
2. Crie sua conta de administrador em Authentication e copie o **UID** do usuário.
3. O arquivo `.env.local` deste pacote já contém os seis valores públicos da configuração Web que você forneceu. Preencha apenas `VITE_ADMIN_UIDS` com o UID da sua conta.
4. Abra `firestore.rules`, substitua `SUBSTITUA_PELO_UID_DO_ADMIN` pelo mesmo UID e publique as regras no console do Firestore. O UID na interface apenas controla a apresentação do painel; a regra do Firestore protege as gravações.
5. Reinicie o servidor local. Entre em **Desenvolvedor**, faça login, cadastre o WhatsApp com `55` + DDD + número, troque os produtos e publique. Isso criará `site/main` no Firestore. Antes disso, o catálogo de exemplo é exibido.
6. Em Authentication, adicione os domínios usados em **Settings > Authorized domains**. Para Netlify, configure as mesmas variáveis `VITE_*` em **Site configuration > Environment variables** e faça novo deploy. O arquivo `netlify.toml` já contém o comando de build e redirecionamento SPA.

**Atenção:** Os produtos, preços e fotografias iniciais são demonstrativos. Sem Firebase, a edição salva apenas neste navegador. Sem número de WhatsApp, o checkout permanece indisponível. A loja não recebe pagamento no site: disponibilidade, frete e pagamento são combinados na conversa com o cliente. As fotos de exemplo usam URLs externas do Unsplash; use imagens suas ou licenciadas para operação comercial.

A configuração Web presente em `.env.local` é pública, mas mantenha o arquivo fora do Git para separar ambientes. Nunca envie senha, chave de conta de serviço ou arquivo JSON de administrador ao Codex. A configuração Web (`apiKey`, `authDomain`, `projectId`, `appId`) é identificadora pública do cliente; a segurança depende das regras do Firestore e do Auth.
