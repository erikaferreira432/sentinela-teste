# Hospital Sentinela — versão revisada

## O que foi melhorado
- Identidade visual unificada em verde-petróleo, off-white e dourado discreto.
- Novo CSS compartilhado, responsivo e com estados de foco/teclado.
- Tela de login integrada ao CSS comum.
- O servidor usado pelo Docker agora compartilha as rotas completas da API, incluindo internação e alta, evitando a divergência entre `backend/server.js` e `api/index.js`.
- Senhas não são mais modificadas com `trim()` durante a autenticação.
- Rotas de internação, alta e verificação de saúde incluídas nas regras de reescrita da Vercel.
- Verificação sintática dos dois arquivos JavaScript do servidor com `node --check`.

## Como executar localmente
1. Instale Node.js 20 ou superior.
2. No diretório `sentinela-main`, execute `npm install`.
3. Execute `npm start`.
4. Acesse `http://localhost:3002`.

Com Docker: `docker compose up --build` e acesse `http://localhost:3010`.

## Usuários de demonstração
O banco inicial contém os usuários de demonstração `triagem`, `medico` e `atendimento`, com a senha `123`. **Troque essas credenciais antes de qualquer apresentação pública ou uso real.**

## Limitações importantes antes da banca
Este projeto é um protótipo acadêmico, não um sistema hospitalar pronto para produção. A autenticação atual valida usuário e senha, mas ainda precisa de sessões seguras, autorização por perfil em cada rota, hash de senhas (Argon2id/bcrypt), proteção contra tentativas repetidas e trilha de auditoria. O banco JSON também deve ser substituído por banco transacional com backups e migrações.

O módulo `almoxarifado.html` está incompleto no projeto recebido e não possui rotas de estoque correspondentes no backend. Não foi apresentado como funcional nem foram inventadas operações para simular funcionamento. A classificação de risco da triagem é uma regra demonstrativa e não deve orientar atendimento clínico real; precisa ser validada por profissionais e protocolo institucional.

Antes da defesa, use somente dados fictícios. O arquivo `backend/db.json` original foi preservado, portanto verifique e substitua qualquer dado pessoal nele antes de compartilhar o projeto.
