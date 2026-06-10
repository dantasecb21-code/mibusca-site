# Publicar no GitHub Pages — passo a passo

✅ **Já feito por mim:** a pasta já é um repositório Git com o primeiro commit pronto
(`Primeira versao do site Mibusca`). O workflow em `.github/workflows/deploy.yml` publica
o site no GitHub Pages **a cada push** na branch `main`.

Falta só conectar ao GitHub e enviar — isso depende da sua autenticação.

## 1. Criar o repositório no GitHub

Acesse https://github.com/new e crie um repositório **vazio** (sem README, sem .gitignore),
por exemplo `mibusca-site`. Pode ser público ou privado.

## 2. Conectar e enviar (rode no terminal, dentro da pasta Site)

> Abra o PowerShell/Terminal em `C:\Users\Matheus\Claude\Projects\Site`

```bash
git remote add origin https://github.com/SEU-USUARIO/mibusca-site.git
git push -u origin main
```

Troque `SEU-USUARIO` pelo seu usuário. No push o GitHub pede login ou um Personal Access
Token (crie em https://github.com/settings/tokens, com permissão de `repo`).

> Já existe commit; **não** precisa rodar `git init`, `git add` nem `git commit` de novo.

## 3. Ativar o GitHub Pages

No repositório: **Settings → Pages → Build and deployment → Source: GitHub Actions**.

O Actions roda sozinho e publica. A URL aparece em Settings → Pages
(ex.: `https://SEU-USUARIO.github.io/mibusca-site/`).

## 4. (Opcional) Usar o domínio mibusca.com.br

⚠️ Hoje `mibusca.com.br` aponta para o WordPress atual. Só aponte o domínio para o Pages
quando quiser **substituir** o site atual: Settings → Pages → Custom domain → `mibusca.com.br`,
e ajuste o DNS conforme o GitHub indicar.

## Dia a dia (a cada alteração)

Depois do setup, publicar é só:

```bash
git add .
git commit -m "descrição da alteração"
git push
```

O deploy no Pages acontece automaticamente após o push.

---

### Sobre eu fazer commit + deploy automaticamente

O **commit** eu consigo fazer (e já fiz). O **push/deploy** exige sua autenticação no GitHub,
que não fica disponível no meu ambiente. Para eu assumir o push a cada alteração, você pode:
me fornecer um Personal Access Token do GitHub nesta conversa, **ou** deixar o repositório
conectado e rodar `git push` você mesmo após eu commitar. Sem isso, use os comandos acima.
