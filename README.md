# -Criando-um-Dashboard-corporativo-com-integracao-com-MySQL-e-Azure
 Criando um Dashboard corporativo com integração com MySQL e Azure - NTT DATA

 Descrição do desafio módulo 3 – Processamento de Dados Simplificado com Power BI

1. Criação de uma instância na Azure para MySQL

2. Criar o Banco de dados com base disponível no github

3. Integração do Power BI com MySQL no Azure

4. Verificar problemas na base a fim de realizar a transformação dos dados

Diretrizes para transformação dos dados

1. Verifique os cabeçalhos e tipos de dados

2. Modifique os valores monetários para o tipo double preciso

3. Verifique a existência dos nulos e analise a remoção

4. Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente

5. Verifique se há algum departamento sem gerente

6. Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas

7. Verifique o número de horas dos projetos

8. Separar colunas complexas

9. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção

10. Neste processo elimine as colunas desnecessárias.

11. Realize a junção dos colaboradores e respectivos nomes dos gerentes . Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo.

12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores

13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.

14. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir.

 No contexto do Power BI e da transformação de dados, a diferença entre mesclar (merge) e atribuir (append) está relacionada ao tipo de operação que você está realizando nas tabelas.

Mesclar vs. Atribuir
Mesclar (Merge):

O recurso de mesclagem é utilizado para combinar dados de duas ou mais tabelas que compartilham uma ou mais colunas em comum (chaves). Neste caso, você está essencialmente enriquecendo uma tabela com informações adicionais de outra tabela.
Por exemplo, ao mesclar a tabela de colaboradores (employees) com a tabela de departamentos (departments), você pode adicionar informações sobre qual departamento cada colaborador pertence. Essa operação é crucial quando você precisa que cada registro na tabela resultante tenha informações contextuais (como nome do departamento ou localização) associadas a ele.
A mesclagem é ideal para relacionamentos entre tabelas, como um relacionamento um-para-muitos (um departamento pode ter vários colaboradores).
Atribuir (Append):

Atribuir é utilizado para unir dados de duas ou mais tabelas que têm a mesma estrutura, ou seja, as mesmas colunas. Essa operação é útil quando você deseja combinar dados semelhantes em uma única tabela, como a adição de novos registros de vendas de diferentes meses em uma única tabela de vendas.
Não se destina a enriquecer os dados, mas sim a agregar registros que têm o mesmo formato.
Por que usar mesclar neste caso?
Combinação Contextual: No item 13, você está mesclando os nomes dos departamentos e localização, o que cria uma nova tabela que contém informações mais específicas e contextualizadas sobre cada departamento, facilitando futuras análises e modelagens.
Estrutura Relacional: Como a mesclagem cria um relacionamento entre as tabelas, ela permite que você mantenha as relações adequadas no modelo de dados, essencial para a construção de relatórios e dashboards eficazes no Power BI.
Resumindo
No caso mencionado, você não está apenas somando dados semelhantes (como faria com atribuições), mas está enriquecendo os dados existentes com informações de outra tabela. Portanto, o uso de mesclagem é a abordagem correta para integrar as informações de maneira significativa e relacional.   

15. Agrupe os dados a fim de saber quantos colaboradores existem por gerente

16. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela

    * FERRAMENTAS UTILIZADAS:
```
. Microsoft Azure
. MySQL
. Power BI
. Power Query 
