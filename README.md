# Automacao-de-Testes-de-Modelos-de-Dados-no-DBT

Aqui darei ênfase a uma das mais importantes funcionalidades do DBT, a capacidade de executar testes automatizados.
Os testes automatizados no DBT são verificações programáticas que ajudam a garantir a qualidade e a integridade dos dados durante o processo de transfprmação. Com esses testes, é possivel identificar inconsistências, valores inesperados e problemas de qualidade que possam impactar a análise de dados.

* Tipos de testes no DBT

1. Testes Nativos
2. Teste Personalizados
3. Teste de Dados Adicionais

📚 Programa utilizado

Docker

![Captura de tela 2025-01-05 135649](https://github.com/user-attachments/assets/aeac900c-82e2-44a7-a1a5-e39ce35b7639)

DB Browser for SQLite

![Captura de tela 2025-01-05 142725](https://github.com/user-attachments/assets/0d7c959c-3a50-4a2a-ab16-5408d77523dd)

Iniciamos abrindo o terminal no docker e inicializamos com "dbt init lab8". E apos vamos para a pasta "cd /root/.dbt" e editamos o arquivo profiles.yml (localizado em ~/.dbt/profiles.yml) para adicionar uma configuração para o SQLite com "vi profiles.yml" para adicionar isso:

![Captura de tela 2025-01-05 140714](https://github.com/user-attachments/assets/5f67e6e3-a8c3-4a6a-a64e-d8509ef044e6)

Agora criaremos a pasta de dev e prod com os comandos:

mkdir dados-dev

mkdir dados-prd

E na pasta de dados prd ciaremos o banco de cados (arquivi na pasta de dados).

Com tudo pronto vamos para a pasta "cd /dsa/lab8" e inicializaremos com o comando "dbt debug".

![Captura de tela 2025-01-05 141456](https://github.com/user-attachments/assets/18892602-a9c4-4f48-8b37-2de90e769dea)

Com isso feito passaremos os dados para as pastas criadas e dar inicio ao DBT (lembrando de excluir o arquivo de exemplo da pasta models). 

* Primeiro passaremos os models de clientes, pedidos e produtos

![Captura de tela 2025-01-05 142452](https://github.com/user-attachments/assets/56eb1e8b-947a-4e63-90d0-acdcb6b73c80)

Com isso feito usaremos o "dbt rum" e inicializaremos

![Captura de tela 2025-01-05 142624](https://github.com/user-attachments/assets/a5452171-125e-4374-bb36-c849414f2743)

Assim agora inicializaremos o DB Browser e verificar se as Views foram criadas com o banco de dados da pasta dev.

![image](https://github.com/user-attachments/assets/a6c22244-785e-45b1-a3e2-48dc0088bb83)

📚 Preparando os testes nativos

Os testes tem que ser validados pela area de negocios da empresa (teste mais basico)

![image](https://github.com/user-attachments/assets/8ad91e1c-d856-4172-8bb6-1eb42f28c271)

![image](https://github.com/user-attachments/assets/80f54c84-ff36-46d8-97a8-947c7f33a71b)

![image](https://github.com/user-attachments/assets/8b1d88ee-c861-4762-a506-dd7f6dd2f74c)

📚 Preparando os testes customizados

Aqui iremos customizar os teste (codigos na pasta tests)

![image](https://github.com/user-attachments/assets/69bd4b0b-83f7-454c-983a-732ae712525d)

📚 Testes de Regras de Negócio via Macro

Estar regras de negócio via macros é uma abordagem prática para automatizar verificações e validar comportamentos esperados em sistemas (codigo na pasta macros). 

![image](https://github.com/user-attachments/assets/db5acb59-6093-4708-a38d-ca234afaf797)

📚 Comando para o HULK

Comando que envia para o banco de dados:

![image](https://github.com/user-attachments/assets/58db0103-08f7-474d-a74f-abf8c8c58663)

📚 Testando o DBT

No docker inicializaremos com dbt test

![image](https://github.com/user-attachments/assets/bd48d06e-659a-45ae-80ef-e6459244bc89)

![image](https://github.com/user-attachments/assets/22349061-2485-44e0-a9ce-b8893af47d87)

Se tudo estiver correto migramos os dados de DEV para producão e finalizamos o projeto com o deploy "dbt run --target prod".
