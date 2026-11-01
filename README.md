# NEXUS AI — projeto inicial Android + servidor

Este pacote contém:
- Aplicativo Android (WebView) com interface própria.
- Chat em que o usuário escolhe Gemini ou DeepSeek.
- Histórico local no aparelho.
- Servidor Node.js que mantém as chaves de API fora do APK.

## Importante
O projeto é um ponto de partida funcional, mas **não vem com chaves de API nem servidor publicado**. Para receber respostas reais, é necessário:
1. Criar uma chave oficial do Gemini e/ou DeepSeek.
2. Configurar as chaves no servidor, nunca no aplicativo.
3. Publicar o servidor em um serviço HTTPS.
4. Abrir Configurações no app e informar a URL HTTPS do servidor.

Não coloque chaves secretas no APK, no HTML ou em repositórios públicos.

## Servidor
Requisitos: Node.js 20+.

```bash
cd server
npm install
```

Crie `server/.env` com base em `.env.example` e execute:

```bash
npm start
```

Para testar localmente, o servidor responde em `http://localhost:3000`.
Em produção, use HTTPS. O app Android deve apontar para a URL pública HTTPS.

## Android
Abra a pasta `android/` no Android Studio, aguarde a sincronização do Gradle e compile:
Build > Build Bundle(s) / APK(s) > Build APK(s).

Requisitos: Android Studio com Android SDK 35 e JDK 17.

## Integrações disponíveis nesta primeira versão
- Gemini: endpoint oficial `generateContent`.
- DeepSeek: endpoint oficial `/responses`.

As demais ferramentas aparecem no catálogo como atalhos para seus sites oficiais; não são apresentadas como APIs já integradas.
