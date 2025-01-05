# Automacao-de-Testes-de-Modelos-de-Dados-no-DBT

Aqui darei ênfase a uma das mais importantes funcionalidades do DBT: a capacidade de executar testes automatizados.
Os testes automatizados no DBT são verificações programáticas que ajudam a garantir a qualidade e a integridade dos dados durante o processo de transformação. Com esses testes, é possível identificar inconsistências, valores inesperados e problemas de qualidade que possam impactar a análise de dados.

* Tipos de testes no DBT

1. Testes Nativos
2. Teste Personalizados
3. Teste de Dados Adicionais

📚 Programa utilizado

Docker

![Captura de tela 2025-01-05 135649](https://github.com/user-attachments/assets/aeac900c-82e2-44a7-a1a5-e39ce35b7639)

DB Browser for SQLite

![Captura de tela 2025-01-05 142725](https://github.com/user-attachments/assets/0d7c959c-3a50-4a2a-ab16-5408d77523dd)

Iniciamos abrindo o terminal no Docker e inicializamos com o comando dbt init lab8. Em seguida, acessamos a pasta com cd /root/.dbt e editamos o arquivo profiles.yml (localizado em ~/.dbt/profiles.yml) com o comando vi profiles.yml para adicionar a configuração:

![Captura de tela 2025-01-05 140714](https://github.com/user-attachments/assets/5f67e6e3-a8c3-4a6a-a64e-d8509ef044e6)

Agora, criaremos as pastas de desenvolvimento e produção com os comandos:

mkdir dados-dev

mkdir dados-prd

Na pasta de dados de produção, criaremos o banco de dados (arquivo dentro da pasta de dados).

Com tudo pronto, vamos para a pasta cd /dsa/lab8 e inicializamos com o comando dbt debug.

![Captura de tela 2025-01-05 141456](https://github.com/user-attachments/assets/18892602-a9c4-4f48-8b37-2de90e769dea)

Em seguida, transferimos os dados para as pastas criadas e iniciamos o DBT (lembrando de excluir o arquivo de exemplo da pasta models).

* Primeiro passaremos os models de clientes, pedidos e produtos

![Captura de tela 2025-01-05 142452](https://github.com/user-attachments/assets/56eb1e8b-947a-4e63-90d0-acdcb6b73c80)

Com isso feito usaremos o "dbt rum" para inicializar o processo.

![Captura de tela 2025-01-05 142624](https://github.com/user-attachments/assets/a5452171-125e-4374-bb36-c849414f2743)

Agora, abrimos o DB Browser para verificar se as Views foram criadas no banco de dados da pasta de desenvolvimento.

![image](https://github.com/user-attachments/assets/a6c22244-785e-45b1-a3e2-48dc0088bb83)

📚 Preparando os testes nativos

Os testes precisam ser validados pela área de negócios da empresa (teste mais básico).

![image](https://github.com/user-attachments/assets/8ad91e1c-d856-4172-8bb6-1eb42f28c271)

![image](https://github.com/user-attachments/assets/80f54c84-ff36-46d8-97a8-947c7f33a71b)

![image](https://github.com/user-attachments/assets/8b1d88ee-c861-4762-a506-dd7f6dd2f74c)

📚 Preparando os testes customizados

Aqui, iremos customizar os testes (códigos na pasta tests).

![image](https://github.com/user-attachments/assets/69bd4b0b-83f7-454c-983a-732ae712525d)

📚 Testes de Regras de Negócio via Macro

Estas regras de negócio via macros são uma abordagem prática para automatizar verificações e validar comportamentos esperados em sistemas (código na pasta macros).

![image](https://github.com/user-attachments/assets/db5acb59-6093-4708-a38d-ca234afaf797)

📚 Comando para o HULK

Comando que envia os dados para o banco de dados:

![image](https://github.com/user-attachments/assets/58db0103-08f7-474d-a74f-abf8c8c58663)

📚 Testando o DBT

No Docker, inicializamos os testes com o comando dbt test.

![image](https://github.com/user-attachments/assets/bd48d06e-659a-45ae-80ef-e6459244bc89)

![image](https://github.com/user-attachments/assets/22349061-2485-44e0-a9ce-b8893af47d87)

Se tudo estiver correto, migramos os dados de desenvolvimento para produção e finalizamos o projeto com o deploy "dbt run --target prod".
