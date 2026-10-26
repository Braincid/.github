# Braincid

> Uma plataforma de aprendizagem para transformar conteúdos em revisões simples,
> organizadas e consistentes.

O **Braincid** ajuda pessoas a estudar no próprio ritmo por meio de **decks** e
**flashcards**. A experiência combina organização de conteúdos, repetição
espaçada, recursos para idiomas e integrações nativas para tornar a revisão mais
prática no navegador e no celular.

## O que é possível fazer

- Criar, editar e organizar decks de estudo.
- Criar cards com frente e verso para revisar conteúdos importantes.
- Estudar com ciclos de repetição espaçada.
- Criar decks de idiomas com tradução automática.
- Importar decks de CSV, TSV, Excel, PDF ou TXT.
- Exportar decks em CSV.
- Ouvir o conteúdo dos cards com leitura em voz alta.
- Usar o produto no navegador ou pelo aplicativo nativo.

## Ecossistema

| Projeto | Responsabilidade | Tecnologias principais |
| --- | --- | --- |
| **Frontend** | Interface web, autenticação, decks, cards, estudo, importação e administração. | React, TypeScript, Bootstrap |
| **Backend** | API, regras de negócio, autenticação, revisão espaçada e integração de tradução. | Laravel, PHP, Sanctum |
| **Braincid Native** | Aplicativo Android e iOS que carrega a experiência web com recursos nativos. | React Native, WebView, Kotlin, Objective-C |

## Experiência nativa

O aplicativo **Braincid Native** estende o frontend com recursos do dispositivo:

- leitura de cards com a voz disponível no sistema;
- gravação de áudio quando necessária;
- exportação de decks para arquivos CSV;
- notificações e lembretes de estudo;
- sincronização de idioma, preferências e status bar com a WebView;
- proteção de captura de tela para conteúdos temporários.

## Como a arquitetura funciona

```text
Usuário
  │
  ├── Frontend Web (React) ──────► API (Laravel) ──────► Banco de dados
  │
  └── Aplicativo Native (React Native + WebView)
          └── recursos do dispositivo: áudio, downloads, notificações e permissões
```

O frontend e o aplicativo nativo compartilham a mesma experiência principal. No
app, uma bridge entre a WebView e o React Native habilita funcionalidades que
precisam de acesso ao sistema operacional.

## Para contribuir

Cada aplicação possui seu próprio repositório. Execute comandos, testes e Git
na pasta do projeto que será alterado.

```bash
# Frontend
cd frontend
npm start
npm test -- --watchAll=false
npm run build

# Backend
cd backend
php artisan serve
php artisan test

# Aplicativo nativo
cd braincid-native
npm start
npm run android
# ou npm run ios
```

Antes de abrir uma contribuição, confirme os testes relevantes, não inclua
credenciais ou arquivos `.env` e descreva claramente alterações de API,
migrations ou configurações necessárias.

---

**Braincid — aprenda mais, esqueça menos.**
