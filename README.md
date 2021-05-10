# listmod - Lista de Módulos

SEGUEM PASSOS PARA O DESAFIO 2

1 - Entrar no diretório 'listmod-2' do repositório disponibilizado;

2 - Executar o comando: 
    docker-compose up

3 - Após finalizado o processo para subir os serviços 'my-mysql', 'back-end' e 'front-end', acessar no browse: localhost:8000

OBSERVAÇÕES:

1 - O código fonte do back-end e front-end estão nas pastas '/listmod/back-end/listmod' e '/listmod/front-end/listmod' respectivamente;

2 - No meu ambiente fiz vários testes com relaçao ao tempo, 40 segundos foi o suficiente quando já tenho a imagem do mysql, com um tempo menor, tanto o back-end quanto o front-end davam problema ao subir, por esse motivo havia acrescentado no 'docker-compose.yaml' restart 'always' nos serviços 'back-end' e 'front-end'.
