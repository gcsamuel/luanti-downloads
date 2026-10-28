# Página de Downloads do Luanti

Página HTML simples e auto-contida com os links de download do **Luanti** (antes Minetest) para todos os sistemas:

- Windows
- macOS
- Linux
- Android (arquivo APK)
- Google Play Store
- Apple App Store (iOS)

Estilo inspirado no site [Instituto Gênio Cristão](https://geniocristao.com.br/): limpo, profissional, com cabeçalho, cards de download, seção de como instalar e rodapé com contatos e redes sociais.

## Estrutura

```
igc/
├── index.html      # Página única (HTML + CSS embutido, sem dependências externas)
├── README.md       # Este arquivo
└── downloads/      # Arquivos oficiais do Luanti (ja baixados)
    ├── luanti-5.17.0-win64.zip              # Windows 64-bit (~17 MB)
    ├── luanti-5.17.0_macos12.3_arm64.zip    # macOS Apple Silicon (~13 MB)
    ├── luanti-5.17.0-arm64-v8a.apk          # Android arm64 (~17 MB)
    └── luanti-linux-info.tar.xz             # Linux: guia de instalacao (~0.5 KB)
```

A página é **100% auto-contida**: todo o CSS está dentro do `index.html` e não há imagens ou arquivos externos. Isso é ideal para intranet.

### Download direto (sem redirecionamento)

Os botões de **Windows, Mac e Android** apontam para arquivos oficiais do Luanti 5.17.0 já hospedados na pasta `downloads/`, com o atributo `download`. Ao clicar, o navegador faz o download direto do arquivo, sem abrir outra página.

**Linux**: não há um instalador único oficial para Linux no GitHub. O link baixa um guia (`luanti-linux-info.tar.xz`) com instruções de instalação via Flatpak, AppImage ou pacotes da distro, além do link para o site oficial.

**Google Play Store** e **Apple App Store** são lojas externas: não existem arquivos diretos para download, então esses botões abrem a página da loja (não há como fazer download direto delas por segurança do navegador).

Os arquivos já foram baixados e estão prontos. Basta publicar no GitHub ou copiar a pasta `igc/` para o servidor da sua intranet.

## Como colocar no GitHub

### 1. Crie o repositório

1. Acesse https://github.com e faça login.
2. Clique em **+ → New repository**.
3. Nomeie o repositório, por exemplo: `luanti-downloads`.
4. Escolha **Public** (ou Private, se for apenas para intranet).
5. Não inicialize com README (já temos os arquivos locais).
6. Clique em **Create repository**.

### 2. Envie os arquivos

No seu terminal, dentro da pasta `/home/zoro/Documents/igc`:

```bash
git init
git add .
git commit -m "pagina de downloads do luanti"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/luanti-downloads.git
git push -u origin main
```

Substitua `SEU-USUARIO` pelo seu nome de usuário do GitHub.

Alternativamente, você pode enviar os arquivos diretamente pelo site do GitHub (botão "upload files").

### 3. Ative o GitHub Pages

1. No repositório no GitHub, vá em **Settings → Pages**.
2. Em **Build and deployment → Source**, selecione **Deploy from a branch**.
3. Escolha a branch `main` e a pasta `/ (root)`.
4. Clique em **Save**.

Após alguns instantes, o GitHub informará a URL da sua página, algo como:

```
https://SEU-USUARIO.github.io/luanti-downloads/
```

## Como usar na intranet

Como a página é um único arquivo HTML sem dependências externas, você tem várias opções para publicar na intranet:

### Opção A — Servir via GitHub Pages (mais simples)
Use a URL gerada acima (`https://SEU-USUARIO.github.io/luanti-downloads/`). Basta que os computadores da intranet tenham acesso à internet para acessar o GitHub Pages.

### Opção B — Copiar o `index.html` para um servidor interno
Se a intranet não tem internet ou você quer hospedar localmente:
1. Copie o arquivo `index.html` para qualquer servidor web interno (IIS, Apache, Nginx, etc.).
2. Exemplo no IIS: coloque em `C:\inetpub\wwwroot\luanti\` e acesse via `http://servidor-interno/luanti/`.
3. Exemplo no Apache/Nginx: coloque em `/var/www/html/luanti/` e acesse via `http://servidor-interno/luanti/`.

### Opção C — Abrir diretamente como arquivo
Em último caso, pode distribuir o `index.html` e abri-lo diretamente no navegador (duplo clique), embora isso não seja recomendado para uso coletivo em rede.

## Personalização

- **Links de download:** Verifique periodicamente os links no `index.html`, especialmente os do GitHub Releases (`https://github.com/luanti-org/luanti/releases/latest`), pois apontam para a versão mais recente.
- **Lojas:** Os links da Google Play e Apple App Store podem mudar conforme o app for renomeado de "Minetest" para "Luanti". Atualize conforme necessário.
- **Cores:** Edite as variáveis CSS no topo do `<style>` (`--primary`, `--dark`, etc.) para mudar a identidade visual.

## Licença

Esta página é um projeto independente de utilidade para download. O Luanti é um software livre de código aberto e esta página não é afiliada oficialmente ao projeto Luanti.
