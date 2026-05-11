# TOPGAMES PayGo

Projeto Next.js para venda de recargas de jogos: Free Fire, PUBG Mobile e COD Mobile.

## Funcionalidades

- Visual premium com tema TOPGAMES.
- Logo TOPGAMES incluído.
- Imagens de capa e pacotes incluídas.
- Pacotes Free Fire, PUBG e COD.
- Carrinho, checkout e confirmação de pedido.
- Integração pronta com Paysuite via API PayGo ou direta.
- Deploy pronto para Vercel.

## Instalação

```bash
npm install
npm run dev
```

Abrir:

```bash
http://localhost:3000
```

## Teste

```bash
npm run test
```

## Deploy na Vercel

1. Suba este projeto no GitHub.
2. Na Vercel, clique em **Add New Project**.
3. Selecione o repositório.
4. Adicione as variáveis de ambiente.
5. Faça deploy.
6. Em **Settings > Domains**, adicione:

```txt
topgames.paygo.co.mz
```

No DNS do domínio `paygo.co.mz`, adicione:

```txt
Tipo: CNAME
Nome: topgames
Valor: cname.vercel-dns.com
```

## Variáveis de ambiente

Copie `.env.example` para `.env.local` em desenvolvimento.

### Recomendado: usar a API PayGo já existente

```env
NEXT_PUBLIC_SITE_URL=https://topgames.paygo.co.mz
NEXT_PUBLIC_WHATSAPP_NUMBER=258871002255
PAYMENT_MOCK_MODE=false
PAYGO_API_BASE_URL=https://paygo.co.mz
PAYGO_API_TOKEN=
```

### Alternativa: usar Paysuite direto neste projeto

```env
PAYSUITE_API_URL=https://paysuite.tech/api/v1
PAYSUITE_API_KEY=sua_chave
PAYSUITE_WEBHOOK_SECRET=seu_secret
```

## Desenvolvimento sem pagamentos reais

Ative:

```env
PAYMENT_MOCK_MODE=true
```

Assim o botão de pagamento redireciona para uma página interna de pedido simulado.

## Onde trocar imagens

As imagens ficam em:

```txt
public/assets/capa-games.png
public/assets/freefire-cover.png
public/assets/pubg-cover.png
public/assets/cod-cover.png
public/assets/freefire-diamonds.png
public/assets/pubg-uc.png
public/assets/cod-cp.png
public/assets/logo-topgames.png
```

## Observação importante

Para o webhook atualizar pedidos automaticamente no Firebase/admin, o ideal é manter a lógica principal na tua API PayGo existente. Este projeto já consegue chamar essa API por `PAYGO_API_BASE_URL`.
