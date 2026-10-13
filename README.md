# Thoni Arquitetura — Landing Page Premium

Landing page de alta conversão desenvolvida para a arquiteta **Meryellen Thoni Melotto** (**Thoni Arquitetura**), com posicionamento sofisticado, foco em arquitetura comercial (consultórios, estética, odontologia, clínicas e lojas) e apresentação de projetos residenciais selecionados.

---

## 🏛️ Stack Técnica

- **Framework:** React 18 + TypeScript + Vite
- **Estilização:** CSS puro modular com tokens arquitetônicos modernos (Cormorant Garamond + Montserrat)
- **Desempenho:** Carregamento otimizado de imagens, lazy loading nativo, zero dependências pesadas de UI
- **SEO & Tráfego:** Metatags completas, OpenGraph, JSON-LD Schema.org (`ArchitecturalService` + `LocalBusiness`), `robots.txt`, `sitemap.xml`
- **Analytics:** DataLayer pronto para Google Tag Manager (GTM) e Google Analytics 4 (GA4) com tracking de cliques no WhatsApp, trocas de filtro e aberturas do lightbox

---

## 🚀 Como Executar Localmente

### Pré-requisitos
- Node.js 18+ instalado.

### Passo a passo
1. Abra o terminal na pasta do projeto:
   ```bash
   cd "C:\Users\Romano\.gemini\antigravity\scratch\thoni-arq"
   ```

2. Instale as dependências (se ainda não tiver feito):
   ```bash
   npm install
   ```

3. Inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```
   Acesse a URL indicada (geralmente `http://localhost:5173`).

4. Para gerar a build otimizada de produção:
   ```bash
   npm run build
   ```

---

## 🌐 Publicação e Deploy na Vercel

O projeto já contém o arquivo [`vercel.json`](file:///C:/Users/Romano/.gemini/antigravity/scratch/thoni-arq/vercel.json) configurado com cabeçalhos de segurança (X-Frame-Options, X-Content-Type-Options, Referrer-Policy) e cache estático para fotos e fontes.

### Passo 1: Subir para o GitHub / Git
1. Crie um repositório no seu GitHub (ex: `thoni-arquitetura-lp`).
2. Inicialize e envie os arquivos:
   ```bash
   git init
   git add .
   git commit -m "feat: landing page thoni arquitetura"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/thoni-arquitetura-lp.git
   git push -u origin main
   ```

### Passo 2: Importar na Vercel
1. Acesse [vercel.com](https://vercel.com) e faça login.
2. Clique em **"Add New..." > "Project"**.
3. Selecione o repositório criado.
4. O framework detectará automaticamente **Vite**.
5. Clique em **"Deploy"**.

---

## 🌍 Configuração de Domínio no Registro.br (`thoniarq.com.br`)

Para conectar o domínio próprio oficial:

1. Na Vercel, acesse: **Settings > Domains**.
2. Digite `thoniarq.com.br` e `www.thoniarq.com.br` e clique em **Add**.
3. A Vercel exibirá os registros DNS necessários:
   - **Registro A (para thoniarq.com.br):**
     - Nome: `@` (ou em branco)
     - Tipo: `A`
     - Valor / IP: `76.76.21.21`
   - **Registro CNAME (para www.thoniarq.com.br):**
     - Nome: `www`
     - Tipo: `CNAME`
     - Valor: `cname.vercel-dns.com.`
4. Acesse o painel do **[Registro.br](https://registro.br)**:
   - Localize o domínio `thoniarq.com.br`.
   - Na seção **DNS**, selecione **Configurar Endereçamento**.
   - Adicione os registros `A` e `CNAME` informados pela Vercel.
   - Salve as alterações.
5. A propagação leva normalmente entre 30 minutos e algumas horas, e a Vercel emitirá o certificado SSL (HTTPS) automaticamente.

---

## 📊 Configuração de Tráfego Pago & Analytics (GTM / GA4 / Meta Ads)

### 1. Inserir o ID do Google Tag Manager
No arquivo [`index.html`](file:///C:/Users/Romano/.gemini/antigravity/scratch/thoni-arq/index.html):
- Substitua `GTM-XXXXXXX` pelo ID oficial do seu contêiner GTM (no `<head>` e no `noscript` do `<body>`).

### 2. Eventos Rastreados via dataLayer
O projeto já dispara eventos automáticos no console/dataLayer:
- `whatsapp_click`: disparado quando o visitante clica em qualquer botão de contato, registrando o local (`hero`, `header`, `floating`, `final_cta`, `footer`).
- `filter_change`: disparado quando o visitante navega entre categorias do portfólio (`all`, `comercial`, `residencial`).
- `portfolio_view`: disparado ao abrir qualquer imagem no modal de alta resolução.

No GTM, basta criar um **Acionador de Evento Personalizado** para `whatsapp_click` e vincular à sua tag de conversão do **Google Ads (lead)** e do **Meta Pixel (Contact)**.
