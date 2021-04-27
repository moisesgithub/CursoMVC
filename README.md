# BootCamp LocalizaLabs .NET by https://digitalinnovation.one
## _Criando e testando uma aplicação ASP.NET API e publicando na Cloud_

- _Para praticar e fixar os conceitos de como criar uma API usando CSharp no VSCommunity_
- _Fiz um passo a passo de como fazer nesse curso_
- _Aberto a sugestões para melhorar o conceito!_

### Adicionando Projeto API

* Com uma solução já aberto do MVC que está neste repositório.
* Vamos clicar com o botão direito do mouse em cima da solução CursoMVC
* Adicionar novo projeto e escolher API Web do ASP.NET Core -> próximo -> nome do projeto Ex.`NomeAPI` -> criar
* Com o projeto criado haverá uma pasta chamada `Controller` -> deleta o arquivo chamado `WeattheForecast`
* Na árvore de arquivos logo abaixo de `Startup` -> deleta também o arquivo `WeattheForecast` não usaremos nesse projeto!

### Habilitando o Swagger
* Com o botão direito do mouse clicar em cima do projeto `NomeAPI`
* Ir até `Gerenciador Pacotes do Nuget...` -> procurar por `Swashbuckle.AspNetCore` -> instalar

### Configurando o Swagger
* Com o botão direito do mouse clicar em cima do projeto `NomeAPI`
* Propriedades -> Compilar -> em Saída marcar `Arquivo de documentação XML:`
* Depurar -> marcar em `Iniciar navegador` -> e mudar a rota para `Swagger` -> salvar tudo!

### Habilitando Dependências
* Ir até o arquivo `Startup` Obs._Nas versões mais nova do `.NET` já estará habilitado!_
* Se não esse é o código que precisa implementar
* Procurar por `services.AddController();`
* e inserir logo abaixo `services.AddSwaggerGen(c=>{c.SwaggerDoc("V1",new OpenApiInfo{Title="NomeAPI",version="v1"});`
* Adicionar também dentro do if `app.UseSwagger();`
* inserir logo abaixo `app.UseSwaggerUI(c=>c.swaggerEndpoint("/swagger/v1/swagger.json","NomeAPI v1"));`

### Adicionar os Controller e Reaproveitar os Models
* Com o botão direito do mouse clicar em cima do projeto `NomeAPI`
* Adicionar -> Referência de Projeto -> e marcar o `NomeAPI`
* Com o botão direito do mouse clicar em cima do pasta `Controller`
* Adicionar -> Novo Item com `Scaffold...`
* Controlador API -> `EntityFramework` -> 
* Adicionar as `Classes` já criadas em CursoMVC

### Compilando os Dois Projetos Juntos
* Solution -> Propriedades -> Projeto de Inicialização
* Marcar Vários Projetos de Inicialização -> 
* Marcar Caixa `Iniciar` para os dois -> `Aplicar` -> `Ok`

### Obs: Ainda falta concluir o projeto!
