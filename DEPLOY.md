# 🚀 Guia Rápido de Deploy na Vercel

## Opção 1: Deploy via GitHub (Recomendado)

### Passo 1: Criar repositório no GitHub
```bash
git init
git add .
git commit -m "Initial commit: Painel PGR"
git branch -M main
git remote add origin https://github.com/seu-usuario/painel-pgr.git
git push -u origin main
```

### Passo 2: Conectar com Vercel
1. Acesse https://vercel.com
2. Faça login com sua conta GitHub
3. Clique em "New Project"
4. Importe o repositório "painel-pgr"
5. Mantenha as configurações padrão (Vite já é detectado automaticamente)
6. Clique em "Deploy"

Pronto! Seu projeto estará online em menos de 1 minuto.

## Opção 2: Deploy via CLI

### Instalar Vercel CLI
```bash
npm install -g vercel
```

### Deploy
```bash
cd painel-pgr
vercel login
vercel
```

Siga as instruções na tela e seu projeto será publicado.

## Opção 3: Deploy Manual (Arrastar e Soltar)

1. Gere o build de produção:
```bash
npm run build
```

2. Acesse https://vercel.com/new
3. Arraste a pasta `dist` para a área de upload
4. Deploy será feito automaticamente

## ⚙️ Configurações da Vercel

O arquivo `vercel.json` já está configurado com:
- Framework: Vite
- Build command: `npm run build`
- Output directory: `dist`
- Rewrites para SPA (Single Page Application)

## 🌐 Após o Deploy

Você receberá uma URL como:
```
https://painel-pgr-xyz123.vercel.app
```

### Configurar domínio personalizado (opcional)
1. Na dashboard do projeto na Vercel
2. Vá em "Settings" > "Domains"
3. Adicione seu domínio personalizado

## 🔄 Atualizações Automáticas

Se você optou pelo deploy via GitHub:
- Todo `git push` para a branch `main` gera um novo deploy automaticamente
- Branches de feature criam previews automáticos
- Pull requests têm preview links únicos

## ✅ Checklist Pré-Deploy

- [ ] Testar localmente com `npm run dev`
- [ ] Verificar build com `npm run build` e `npm run preview`
- [ ] Credenciais estão documentadas no README
- [ ] .gitignore está configurado corretamente
- [ ] Arquivo vercel.json presente

## 🐛 Troubleshooting

### Build falha na Vercel
- Verifique se todas as dependências estão em `package.json`
- Teste o build localmente: `npm run build`
- Verifique os logs de erro na Vercel

### Página em branco após deploy
- Verifique se o `vercel.json` tem as rewrites configuradas
- Abra o Console do navegador para ver erros
- Verifique se todas as rotas do React Router estão corretas

### Erro 404 ao acessar rotas diretas
- Confirme que o `vercel.json` está presente
- As rewrites devem redirecionar todas as rotas para `/index.html`

## 📊 Monitoramento

A Vercel oferece gratuitamente:
- Analytics de acesso
- Web Vitals (Core Web Vitals)
- Logs de function calls
- Métricas de performance

Acesse na dashboard: Seu Projeto > Analytics

## 💡 Dicas

1. **Environment Variables**: Configure na Vercel Dashboard se precisar
2. **Preview Deployments**: Teste mudanças antes de fazer merge
3. **Rollback**: Você pode fazer rollback para qualquer deploy anterior
4. **Custom Domains**: Adicione quantos domínios quiser (grátis)

---

Para mais informações: https://vercel.com/docs
