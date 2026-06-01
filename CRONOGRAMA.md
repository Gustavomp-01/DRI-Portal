# Cronograma — DRI Portal (React + JS)

Projeto refeito do zero (front + back) para prática, sem reutilizar as ferramentas do projeto de referência (que era Angular + TypeScript + Supabase).

- **Início:** segunda-feira
- **Entrega:** quarta-feira
- **Regra de ouro:** não clonar tudo. Uma entidade com CRUD completo + autenticação, bem feita, vale mais que 5 telas pela metade.

---

## Stack escolhida

| Camada | Ferramenta | Observação |
|---|---|---|
| Build/Front | Vite + React (JS) | JS puro, sem TypeScript |
| Navegação | React Router | rotas e rotas protegidas |
| Back-end | Supabase | banco Postgres + Auth + API prontos (este é o "back-end") |
| Estilo | Tailwind CSS (opcional) | acelera e combina com a referência |
| Deploy (opcional) | Vercel ou Netlify | acabamento bom pra entrega |

> **Sobre o "back-end do zero":** com Supabase você não escreve um servidor, mas continua fazendo o trabalho de back-end de verdade — modelar tabelas, definir regras de acesso (RLS), autenticação e as queries. É a forma mais rápida de ter um back-end real funcionando em 3 dias.

---

## Escopo (MVP) — confirmar/ajustar

Suposição de escopo de um portal da DRI / relações internacionais. Ajustar conforme o real:

- [ ] Login / cadastro (Supabase Auth)
- [ ] Listagem de oportunidades (editais / intercâmbios) vinda do banco
- [ ] Página de detalhe de uma oportunidade
- [ ] CRUD completo de uma entidade (criar / editar / excluir)
- [ ] Formulário de inscrição / candidatura *(se sobrar tempo)*

---

## Segunda — Fundação e setup
**Meta do dia:** app rodando, rotas funcionando e Supabase conectado lendo dados de teste.

- [ ] Criar projeto Vite + React e subir o esqueleto no repositório *(~1h)*
- [ ] Organizar pastas: `components/`, `pages/`, `services/` *(incluso acima)*
- [ ] Configurar React Router com as rotas principais *(~1h)*
- [ ] Montar layout base: header, navegação, container das páginas *(~1,5h)*
- [ ] Criar projeto no Supabase e a 1ª tabela (ex.: `oportunidades`) *(~1h)*
- [ ] Conectar o React ao Supabase e fazer um `select` de teste aparecer na tela *(~1,5h)*

---

## Terça — Funcionalidades core
**Meta do dia:** feature principal funcionando de ponta a ponta.

- [ ] Auth: cadastro, login, logout *(~1,5h)*
- [ ] Rotas protegidas (redireciona quem não está logado) *(~1h)*
- [ ] Listagem + página de detalhe lendo do Supabase *(~2h)*
- [ ] Criar nova oportunidade (insert) *(~1h)*
- [ ] Editar e excluir oportunidade (update/delete) *(~1,5h)*

---

## Quarta — Polimento e entrega
**Meta do dia:** entregar.

- [ ] Estilo e responsividade *(~1h)*
- [ ] Estados de loading e erro + validação de formulário *(~1h)*
- [ ] Caça a bugs e casos de borda *(~1,5h)*
- [ ] README: o que é o projeto e como rodar *(~1h)*
- [ ] Commit/push final *(~0,5h)*
- [ ] Deploy na Vercel/Netlify *(opcional, ~1h)*
- [ ] **Buffer** para imprevistos — não preencher, deixar para emergência *(~1,5h)*

---

## Dicas de Supabase (evitar armadilhas)

- [ ] Usar **somente a chave `anon`** no frontend, nunca a `service_role`.
- [ ] Variáveis em `.env`: `VITE_SUPABASE_URL` e `VITE_SUPABASE_ANON_KEY`.
- [ ] Confirmar que `.env` está no `.gitignore` antes do primeiro push.
- [ ] Ativar **RLS (Row Level Security)** na tabela e criar as policies — sem isso as queries voltam vazias e parece bug.
- [ ] Começar com **uma tabela só**; adicionar relações depois, se der tempo.

---

## Plano B (se travar no Supabase na segunda)

Se o Supabase consumir tempo demais, trocar a persistência por `localStorage` ou um JSON mockado para garantir a entrega de quarta. O CRUD e as telas continuam iguais; muda só de onde os dados vêm.
