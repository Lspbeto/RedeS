Aqui está um guia passo a passo detalhado explicando a estrutura de arquivos e os comandos 
necessários para colocar a aplicação de rede social rodando localmente na sua máquina.1.
Pré-requisitosAntes de iniciar, certifique-se de ter o Node.js instalado no seu computador. 
Você pode verificar se ele está instalado abrindo o terminal e digitando:Bashnode -v
Se retornar a versão (ex: v18.x.x ou superior), você está pronto para prosseguir.2. 
Estrutura de Pastas e ArquivosPara que o projeto funcione perfeitamente, crie uma pasta principal para o seu projeto
(por exemplo, rede-social) e organize os arquivos fornecidos exatamente com os seguintes nomes dentro dela:Plaintextrede-social/
├── server.js
├── package.json (será criado no passo 3)
└── public/
    ├── index.html
    ├── feed.html
    ├── style.css
    └── script.js
Nota importante: Os arquivos de interface (index.html, feed.html, style.css e script.js) devem ficar dentro de uma subpasta
chamada public, pois o arquivo server.js está configurado para servir os arquivos estáticos a partir 
dela (app.use(express.static(path.join(__dirname, 'public')))).  
3. Passos para InicializaçãoPasso 1: Inicializar o projeto Node.jsAbra o terminal (Prompt de Comando, PowerShell ou terminal 
do VS Code) na pasta raiz do projeto (rede-social) e execute o comando abaixo para criar o arquivo de configuração do Node (package.json):Bashnpm init -y
Passo 2: Instalar as dependências necessáriasA aplicação utiliza o Express para gerenciar as rotas do 
servidor e o express-session para o controle de sessões e autenticação de usuários. Instale-os executando o seguinte comando
no terminal:   Bashnpm install express express-session
(Opcional: Se desejar que o servidor reinicie automaticamente ao alterar códigos, você pode instalar o nodemon como dependência
de desenvolvimento usando npm install --save-dev nodemon).Passo 3: Configurar o arquivo package.jsonAbra o arquivo package.json
gerado no Passo 1 e adicione o script de inicialização (start) dentro dele para facilitar a execução. O arquivo deve ficar semelhante a isto:JSON{
  "name": "rede-social",
  "version": "1.0.0",
  "description": "Aplicação de rede social simples",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^4.19.2",
    "express-session": "^1.18.0"
  }
}
4. Executando a AplicaçãoCom todos os arquivos organizados e as dependências instaladas, execute o comando de inicialização no terminal:Bashnpm start
Ou diretamente com o Node:Bashnode server.js
Se tudo estiver correto, a mensagem abaixo aparecerá no terminal:Rede Social rodando em http://localhost:3000   
5. Como Acessar e TestarAbra o seu navegador de preferência (Chrome, Firefox, Edge, etc.).Digite o endereço: http://localhost:3000  
Você será direcionado para a tela de login (index.html).   Dica de Acesso Inicial: O código já possui um usuário padrão pré-cadastrado no banco de dados em memória:   Usuário: admin   Senha: 123456   Alternativamente, você pode clicar em "Cadastre-se" para criar uma nova conta de usuário e testar interações entre diferentes perfis (como feed de publicações, comentários, curtidas e status online em tempo real).   
