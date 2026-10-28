# Quadra & Pauta — Organizador pessoal

## Sobre o projeto
O **Quadra & Pauta** é uma aplicação web para organizar atividades pessoais e objetivos em cinco áreas: basquete, jornalismo esportivo, estudos, inglês e tecnologia/IoT. O lema é: **“Disciplina na rotina. Evolução dentro e fora da quadra.”**

A interface usa fundo preto/grafite, destaques laranja e detalhes roxos, com layout responsivo para computador e celular.

## Funcionalidades
- Cadastro e login de usuários com e-mail e senha.
- Criação, leitura, edição e exclusão de atividades (CRUD).
- Categorias: Basquete, Jornalismo, Estudos, Inglês, Tecnologia / IoT e Pessoal.
- Título, detalhes, prioridade e prazo opcional.
- Marcar atividades como concluídas e reabri-las.
- Filtros para todas, pendentes e concluídas.
- Busca por título, descrição e categoria.
- Indicadores de total, pendentes e concluídas.
- Sincronização em tempo real com Cloud Firestore.
- Cada usuário só acessa as próprias atividades, conforme as regras do Firestore.

## Tecnologias
- HTML5, CSS3 e JavaScript puro (sem framework).
- Firebase Authentication (e-mail/senha).
- Cloud Firestore (banco de dados em tempo real).
- Firebase Hosting (publicação recomendada).

## Como executar localmente
1. Instale o Node.js e a Firebase CLI, se ainda não estiverem instalados.
2. Abra esta pasta no Visual Studio Code.
3. Confira `public/firebase-config.js`; ele já está configurado para o projeto Web `quadra-e-pauta`. Se trocar de projeto, substitua os valores pelos dados do app correspondente.
4. No Firebase Console, confirme que Authentication com E-mail/senha está ativo e que o Cloud Firestore foi criado.
5. Execute um servidor local, preferencialmente com a extensão Live Server, ou use `firebase emulators:start` se tiver configurado os emuladores.
6. Abra o endereço local fornecido pelo servidor.

## Serviços Firebase necessários
- **Authentication:** habilitar o provedor E-mail/senha.
- **Cloud Firestore:** criar o banco e publicar as regras do arquivo `firestore.rules`.
- **Hosting:** opcional, mas recomendado para publicar a aplicação.

## Publicar com Firebase Hosting
Na raiz do projeto, execute:

```bash
npm install -g firebase-tools
firebase login
firebase use --add
firebase deploy
```

Confira se o projeto Firebase selecionado é o correto antes de publicar. O `firebase.json` configura a pasta `public` como diretório público.

## Atividade acadêmica — carga horária de 6 horas
**Objetivo geral:** desenvolver aplicações web integrando HTML, CSS e JavaScript com os serviços de back-end do Firebase, incluindo autenticação, banco de dados e hospedagem.

Curso indicado: [HTML, CSS, JavaScript e Firebase: Seja um FullStack developer — Cursa](https://cursa.app/cursos-gratuitos-online/firebase).

O trabalho pede:
1. Realizar o curso e seus exercícios.
2. Desenvolver uma aplicação web com cadastro/login por e-mail e senha e operações CRUD armazenadas no Firestore ou Realtime Database.
3. Se possível, publicar com Firebase Hosting.

### Produto final para entrega
- [ ] Certificado de conclusão do curso em PDF, obtido pela plataforma Cursa.
- [ ] Código-fonte em ZIP ou link para repositório, por exemplo GitHub.
- [x] README com descrição e instruções (este arquivo).
- [ ] Prints ou vídeo curto demonstrando autenticação e CRUD no Firebase.
- [ ] Hospedagem com Firebase Hosting (opcional, recomendada).

## Evidências sugeridas
1. Tela de criação de conta.
2. Login realizado e painel aberto.
3. Atividade nova salva e visível na lista.
4. Edição de uma atividade.
5. Atividade marcada como concluída.
6. Exclusão de uma atividade.
7. Cloud Firestore exibindo os registros de teste. Não mostre senhas nem dados pessoais desnecessários.

## Segurança
As regras do Firestore limitam a leitura e alteração das atividades ao usuário autenticado cujo UID corresponde ao caminho do documento. Não publique senhas ou credenciais privadas. A configuração do app Web fica no front-end, mas a segurança real dos dados depende das regras corretas do Firestore.
