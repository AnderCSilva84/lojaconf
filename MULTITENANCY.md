# Base multiempresa

Cada loja usa um identificador (`storeId`) estável, em letras minúsculas,
números e hífens. A loja original usa `atelie-01`.

## Estrutura no Firestore

```text
stores/{storeId}                         dados públicos da loja
stores/{storeId}/members/{uid}           papel do usuário na loja
users/{uid}                              perfil privado do usuário
site/main                                legado somente para leitura
```

Papéis aceitos em `members`:

- `owner`: edita a loja e gerencia membros;
- `editor`: edita a loja;
- `viewer`: somente acessa recursos privados futuros.

Um membro pode ser desativado com `active: false`.

## Seleção da loja

`VITE_DEFAULT_STORE_ID` define a loja exibida no domínio principal. Para
desenvolvimento e validação, outra loja pode ser aberta com:

```text
https://dominio.example/?store=outra-loja
```

O suporte a subdomínios e domínios personalizados será adicionado em uma
etapa posterior, com um registro seguro de domínios.

## Painel da agência

O superadministrador pode abrir o painel pelo botão **Agência** no rodapé ou
diretamente com `?platform=1`. O painel permite criar lojas, associar o UID do
proprietário, ativar ou suspender ambientes e abrir o editor de cada cliente.

## Migração da primeira loja

Enquanto `stores/atelie-01` ainda não existir, o aplicativo lê `site/main`.
O primeiro salvamento feito pelo superadministrador cria automaticamente
`stores/atelie-01`. O documento legado permanece somente para leitura.

## Segurança

As regras em `firestore.rules` isolam os dados por loja. Leituras do documento
de uma loja ativa são públicas; gravações exigem superadministrador, `owner`
ou `editor` ativo daquela loja. Somente o superadministrador exclui lojas.
