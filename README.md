# DIO - Trilha .NET - Banco de Dados
www.dio.me

## Desafio de projeto
Você é responsável pelo banco de dados de um site de filmes, onde são armazenados dados sobre os filmes e seus atores. Sendo assim, foi solicitado para que você realize uma consulta no banco de dados com o objetivo de trazer alguns dados para análises.

## Proposta
Você precisará realizar 12 consultas ao banco de dados, cada uma retornando um tipo de informação.
O seu banco de dados está modelado da seguinte maneira:

![Diagrama banco de dados](Imagens/diagrama.png)

As tabelas sao descritas conforme a seguir:

**Filmes**

Tabela responsável por armazenar informações dos filmes.

**Atores**

Tabela responsável por armazenar informações dos atores.

**Generos**

Tabela responsável por armazenar os gêneros dos filmes.

**ElencoFilme**

Tabela responsável por representar um relacionamento do tipo muitos para muitos entre filmes e atores, ou seja, um ator pode trabalhar em muitos filmes, e filmes
podem ter muitos atores.

**FilmesGenero**

Tabela responsável por representar um relacionamento do tipo muitos para muitos entre filmes e gêneros, ou seja, um filme pode ter mais de um gênero, e um genêro pode fazer parte de muitos filmes.

## Preparando o banco de dados
Você deverá executar o arquivo **Script Filmes.sql** em seu banco de dados SQL Server, presente na pasta Scripts deste repositório ([ou clique aqui](Script%20Filmes.sql)). Esse script irá criar um banco chamado **Filmes**, contendo as tabelas e os dados necessários para você realizar este desafio.

## Objetivo
Você deverá criar diversas consultas, com o objetivo de retornar os dados a seguir. Abaixo de cada pedido tem o retorno esperado. O seu retorno deve ser igual ao da imagem.

## 1 - Buscar o nome e ano dos filmes

![Exercicio 1](Imagens/1.png)

## 2 - Buscar o nome e ano dos filmes, ordenados por ordem crescente pelo ano

![Exercicio 2](Imagens/2.png)

## 3 - Buscar pelo filme de volta para o futuro, trazendo o nome, ano e a duração

![Exercicio 3](Imagens/3.png)

## 4 - Buscar os filmes lançados em 1997

![Exercicio 4](Imagens/4.png)

## 5 - Buscar os filmes lançados APÓS o ano 2000

![Exercicio 5](Imagens/5.png)

## 6 - Buscar os filmes com a duracao maior que 100 e menor que 150, ordenando pela duracao em ordem crescente

![Exercicio 6](Imagens/6.png)

## 7 - Buscar a quantidade de filmes lançadas no ano, agrupando por ano, ordenando pela duracao em ordem decrescente

![Exercicio 7](Imagens/7.png)

## 8 - Buscar os Atores do gênero masculino, retornando o PrimeiroNome, UltimoNome

![Exercicio 8](Imagens/8.png)

## 9 - Buscar os Atores do gênero feminino, retornando o PrimeiroNome, UltimoNome, e ordenando pelo PrimeiroNome

![Exercicio 9](Imagens/9.png)

## 10 - Buscar o nome do filme e o gênero

![Exercicio 10](Imagens/10.png)

## 11 - Buscar o nome do filme e o gênero do tipo "Mistério"

![Exercicio 11](Imagens/11.png)

## 12 - Buscar o nome do filme e os atores, trazendo o PrimeiroNome, UltimoNome e seu Papel

![Exercicio 12](Imagens/12.png)

---

### Configurando o SQL Server no SQL Server Configuration Manager

1. **Abrir o SQL Server Configuration Manager:**
   - No Windows, vá para o menu Iniciar e procure por "SQL Server Configuration Manager".
   - Clique para abrir o aplicativo.

2. **Verificar as Configurações de Serviço:**
   - No SQL Server Configuration Manager, clique em "SQL Server Services" na barra lateral esquerda.
   - Aqui você verá uma lista de serviços relacionados ao SQL Server. Certifique-se de que os serviços que deseja configurar estão em execução. Se não estiverem, você pode clicar com o botão direito do mouse sobre eles e selecionar "Start" para iniciá-los.

3. **Configurar Protocolos do SQL Server:**
   - Ainda no SQL Server Configuration Manager, expanda "SQL Server Network Configuration" na barra lateral esquerda e clique em "Protocols for [Nome da Instância]".
   - Na janela central, você verá uma lista de protocolos. Certifique-se de que os protocolos que deseja usar estão habilitados (geralmente TCP/IP e Named Pipes). Se não estiverem, clique com o botão direito do mouse sobre o protocolo e selecione "Enable".

4. **Configurar Propriedades do Protocolo TCP/IP:**
   - Clique duas vezes em "TCP/IP" na lista de protocolos.
   - Na guia "Protocolo TCP/IP", verifique se o status está como "Enabled" (Habilitado).
   - Vá para a guia "IP Addresses" e verifique se o IP e a porta que deseja usar estão configurados corretamente. Por exemplo, verifique se o IP é "127.0.0.1" para conexão local ou o IP da máquina para conexões remotas. Verifique também se a porta está configurada corretamente (padrão é 1433).

5. **Reiniciar Serviços do SQL Server:**
   - Depois de fazer todas as configurações necessárias, é recomendável reiniciar os serviços do SQL Server para que as alterações tenham efeito. Para fazer isso, clique com o botão direito do mouse no serviço relevante na lista "SQL Server Services" e selecione "Restart".

6. **Verificar as Configurações de Firewall:**
   - Se estiver configurando para conexões remotas, verifique se as regras de firewall estão configuradas para permitir o tráfego na porta do SQL Server (por padrão, a porta é 1433 para conexões TCP/IP).

7. **Testar a Conexão:**
   - Após realizar todas as configurações, você pode testar a conexão usando o SQL Server Management Studio (SSMS) ou qualquer outra ferramenta de gerenciamento de banco de dados. Certifique-se de que pode se conectar ao servidor usando o endereço IP e a porta configurados.

8. **Concluir:**
   - Depois de seguir esses passos, você deve ter configurado com sucesso o SQL Server usando o SQL Server Configuration Manager.

Certifique-se de revisar e ajustar as configurações conforme necessário para atender aos requisitos específicos do seu ambiente.


## Como Executar Consultas SQL no MSSMS (SQL Server Management Studio)

### Pré-requisitos

Antes de começar, verifique se você tem o seguinte instalado em sua máquina:

- Microsoft SQL Server Management Studio (SSMS)
- Microsoft SQL Server instalado e em execução

### Passo 1: Abrir o Microsoft SQL Server Management Studio (SSMS)

Abra o Microsoft SQL Server Management Studio (SSMS) a partir do menu Iniciar ou usando a pesquisa do Windows.

### Passo 2: Conectar-se ao Servidor SQL

Na janela "Conectar ao Servidor", preencha os seguintes campos:

- **Servidor**: Insira o nome do servidor SQL ao qual você deseja se conectar.
- **Autenticação**: Escolha o método de autenticação, como Autenticação do Windows ou Autenticação do SQL Server.
- **Nome de usuário e Senha**: Selecione e insira as credenciais de login, se aplicável.

Clique em "Conectar" para estabelecer a conexão com o servidor SQL.

### Passo 3: Abrir uma Nova Consulta

No menu superior, clique em "Arquivo" e selecione "Nova Consulta" ou use o atalho `Ctrl + N`. Isso abrirá uma nova janela de consulta onde você pode escrever e executar suas consultas SQL.

### Passo 4: Escrever e Executar Consultas SQL

Na janela de consulta, escreva sua consulta SQL. Por exemplo:

```sql
SELECT * FROM TabelaExemplo;
```


Para executar a consulta, clique no botão "Executar" na barra de ferramentas ou use o atalho `F5`. Isso enviará a consulta para o servidor SQL e exibirá os resultados na parte inferior da janela.

### Passo 5: Analisar Resultados

Após a execução da consulta, você verá os resultados na grade de resultados na parte inferior da janela. Aqui, você pode visualizar e analisar os dados retornados pela sua consulta SQL.

### Passo 6: Fechar a Janela de Consulta

Quando terminar de executar suas consultas, você pode fechar a janela de consulta clicando no botão "Fechar" ou simplesmente fechando a guia da janela.

### Passo 7: Desconectar-se do Servidor SQL (Opcional)

Para desconectar-se do servidor SQL, clique no botão "Conectar" na barra de ferramentas e selecione "Desconectar".

Agora você está pronto para escrever e executar consultas SQL no Microsoft SQL Server Management Studio (SSMS)! Certifique-se de praticar e explorar os recursos adicionais disponíveis no SSMS para aprimorar suas habilidades de consulta SQL.
