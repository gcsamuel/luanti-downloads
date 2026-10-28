# Página de Downloads do Luanti | Instituto Gênio Cristão

Página HTML com a identidade visual do **Instituto Gênio Cristão (IGC)**, contendo downloads do **Luanti** (antes Minetest) para todos os sistemas, além de seções para o **lançamento do livro** e informações sobre o IGC.

## Estrutura

```
igc/
├── index.html      # Página única (HTML + CSS embutido, identidade IGC)
├── README.md       # Este arquivo
└── downloads/      # Arquivos oficiais do Luanti (já baixados)
    ├── luanti-5.17.0.exe              # Windows Instalador (~12 MB)
    ├── luanti-5.17.0-win64.zip        # Windows Portable (~17 MB)
    ├── luanti-5.17.0_macos12.3_arm64.zip  # macOS Apple Silicon (~13 MB)
    ├── luanti-5.17.0-arm64-v8a.apk    # Android (Celular) (~17 MB)
    └── luanti-linux-info.tar.xz       # Linux: guia de instalação (~0.5 KB)
```

## Seções da página

- **Header**: Logo e nome do IGC, navegação
- **Hero**: Apresentação com links para downloads e lançamento do livro
- **Downloads**: Cards por plataforma com download direto (sem redirecionamento)
- **Lançamento do Livro**: Destaque para a nova publicação do IGC
- **Sobre o IGC**: Missão, contato e endereço
- **Footer**: Links rápidos, redes sociais e copyright

## Download direto

Os botões de **Windows, Mac e Android** fazem download direto do arquivo (atributo `download`), sem abrir outra página.

**Windows**: Instalador (.exe) ou Portable (.zip)  
**Linux**: Flatpak, AppImage/.deb via site oficial ou guia local  
**APK**: Apenas para celulares Android  
**Google Play / App Store**: Abrem a página da loja (não há arquivo direto)

## Como publicar no GitHub

```bash
cd /home/zoro/Documents/igc
git init
git add .
git commit -m "Página IGC com downloads do Luanti"
git branch -M main
git remote add origin https://github.com/gcsamuel/luanti-downloads.git
git push -u origin main
```

Depois ative o **GitHub Pages**: Settings → Pages → Branch `main` → Pasta `/ (root)` → Save.

Sua página ficará em: `https://gcsamuel.github.io/luanti-downloads/`

## Uso na intranet

Como a página é auto-contida (sem dependências externas), você também pode copiar a pasta `igc/` inteira para qualquer servidor web interno (IIS, Apache, Nginx) e acessar pelo endereço interno da rede.
