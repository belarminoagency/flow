# belarmino flow — como colocar no ar

App de tarefas da equipe belarmino agency. Funciona no **Android (APK)**, no **iPhone (pelo Safari)** e no **computador (navegador)**, com login, nome e foto para cada pessoa, tudo sincronizado em tempo real.

Sem o passo 2, o app abre em **modo demonstração** (dados de exemplo, só no aparelho).

---

## 1. Publicar o site (GitHub Pages)
1. No GitHub, crie um repositório novo chamado `flow` (público).
2. Envie todos os arquivos desta pasta (index.html, config.js, manifest.json, sw.js, icon-192.png, icon-512.png).
3. Settings → Pages → Branch `main` → Save.
4. O app fica em: `https://belarminoagency.github.io/flow/`

## 2. Ligar o login e a sincronização (Firebase, grátis)
1. Acesse console.firebase.google.com → **Adicionar projeto** → nome `belarmino-flow` (pode desativar o Analytics).
2. **Authentication** → Começar → ative **E-mail/senha**.
3. Authentication → Configurações → **Domínios autorizados** → adicione `belarminoagency.github.io`.
4. **Firestore Database** → Criar banco → modo produção → região `southamerica-east1` (São Paulo).
5. Firestore → aba **Regras** → cole o conteúdo de `firestore.rules`, troque os e-mails da Evelyn e da Emily → Publicar.
6. Configurações do projeto (engrenagem) → **Seus apps** → ícone `</>` (Web) → registre → copie o bloco `firebaseConfig`.
7. Cole esses valores no arquivo `config.js` e envie de novo para o GitHub.

Pronto: o banner de "Modo demonstração" some e cada um cria sua conta.

## 3. Cada pessoa entra
- Abre o link → **Criar conta** → e-mail e senha → escolhe **nome de usuário, função e foto**.
- Só os e-mails listados nas regras conseguem ver e editar as tarefas.
- Pode entrar no celular, no notebook e em outro aparelho ao mesmo tempo com a mesma conta.

## 4. iPhone (sem APK)
Safari → abrir o link → botão **Compartilhar** → **Adicionar à Tela de Início**. Abre em tela cheia, com ícone, igual app.

## 5. APK para Android
1. Acesse **pwabuilder.com** → cole o link do app → Start.
2. Package for stores → **Android** → Download.
3. Dentro do .zip vem o `.apk` para instalar (e o `.aab`, se um dia quiser a Play Store).

O APK abre o mesmo app online, então qualquer atualização no GitHub chega para todos automaticamente.
