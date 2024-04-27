/# MVC do DellAware - lLedTech

# Template Readme para Arquitetura MVC em Markdown
- Nome do Projeto: DellAware
- Descrição: Aplicação web para a Dell Technologies com foco em otimizar a linha de produção, reduzindo pausas e melhorando o treinamento dos funcionários. Além disso, os administradores poderão gerenciar e atualizar manuais, documentos, imagens, vídeos, modelos 3D, etc. Isso permitirá que os funcionários aprendam rapidamente novos processos, mantenham-se atualizados sobre mudanças e revisem informações sobre produtos antigos.
- Arquitetura: MVC (Model-View-Controller)
- Ferramenta de Diagramação: draw.io

### Modelos (Models):
  As três entidades utilizadas no dellAware foram os Manuais, os montadores e os administradores. Os manuais possuem o "id", "nome", "descrição" e "URL" como seus atributos e os montadores, juntamente com os administradores, utilizam o "CPF", "nome", "equipe" e "senha" como atributos.
	A relação entre as entidades do projeto é estabelecida por meio da função que o manual possuí dentro da fábrica, já que é obrigatório que os montadores estudem os manuais, que os administradores deleguem e organizem os manuais e que todos os manuais mantenham-se atualizados e alinhados com a linha de montagem.

### Controladores (Controllers):
Os controladores do DellAware são divididos entre manuais, montadores e administradores. Os montadores têm a responsabilidade de "logar" dentro da plataforma, "ler" e realizar as tarefas dentro de cada manual e "listar" os seus manuais dentro do kanban. Além deles, temos os administradores, que são responsáveis por "adicionar" novos manuais, "logar" na plataforma, "delegar" manuais para diferentes linhas de montagem e/ou funcionários caso necessário, "excluir" manuais muito antigos ou obsoletos e "atualizar" os manuais para manter a linha de montagem ciente de todas as modificações no processo.
	Dentro do controlador "manuais", entende-se que cada responsabilidade aceita parâmetros que modificam e interagem com os modelos e com as views. A partir disso, temos que:

1. "Filtrar": Com os filtros presentes no repositório, o administrador pode pesquisar por um manual e delega-lo para um ou mais funcionários entre as linhas de produção, fazendo com que novos manuais sejam adicionados aos Kanbans dos montadores.

2. "Editar": Por meio do botão editar, os administradores conseguem modificar as informações, os links, as descrições ou qualquer outra coisa dentro de um manual e, dessa forma, atualizá-los para todos os funcionários que possuem esse acesso.

3. "Procurar": Com essa ferramenta, a busca por um manual específico é facilitada para os administradores, facilitando a atribuição deles para os montadores e a organização visual do banco de dados dentro da view.
 
	Agora, dentro do controlador "administradores", temos mais responsabilidades que aceitam parâmetros que modificam e interagem com os modelos e com as views. Ao analisá-las, percebemos que:

1. "adicionar": Por meio do botão adicionar presente no repositório, os administradores conseguem selecionar novos manuais e adicioná-los ao banco de dados da plataforma.

2. "Logar": Na página inicial, tanto os administradores quanto os montadores fazem o seu login com o seu e-mail constitucional e sua senha já definida pela Dell.

3. "Delegar": A partir da funcionalidade delegar presente no repositório, o administrador consegue limitar o acesso de um repositório para funcionários em específico ou deixá-lo público para todas as linhas de montagem, alterando o kanban dos montadores e os seus acessos aos manuais.

4. "Excluir": A partir do botão de excluir dentro do repositório, os manuais podem ser deletados do banco de dados e, consequentemente, não aparecerão mais na homepage do montador e nem no repositório do administrador.

5. "Atualizar": Com essa ferramenta é possível que os administradores atualizem, adicionem ou retirem algo de qualquer um dos manuais disponibilizados na plataforma web. Por meio disso, os montadores podem se manter atualizados do processo e garantir que seu kanban está com a ver~sao mais recente possível do manual.

	Já no controlador "montadores", as responsabilidades atuam da seguinte forma:

1. "Logar": Fazer o login na aplicação web assim como o administrador para ser direcionado a homepage.

2. "Ler": realizar a leitura e o estudo completo dos manuais disponibilizados em "para fazer" ou "fazendo" no kanban.

3. "Listar": Fazer com que o montador tenha o controle de seu kanban listando as tarefas já realizadas dentro de cada manual por meio de checklist e, por consequência, dentro do kanban.

### Views (Views):
  As views são as interfaces em que o usuário irá explorar e interagir com o conteúdo. No caso do DellAware, as views são as seguintes:

- Login: Responsável por permitir que o usuário consiga logar na plataforma;
- Homepage do montador: Local onde o montador verifica seus manuais dentro do kanban e acompanha quais tarefas ainda tem que realiar e quais já foram feitas;
- Dashboard do administrador: Local onde o administrador acompanha o desenvolvimento e desempenho geral da equipe.
- Repositório: Local onde ocorre a delegação dos manuais para as linhas de montagem e permite que o administrador atualize ou adicione manuais.
- Perfil do funcionário: Local onde a foto de perfil, o desempenho e os dados do funcionário são disponibilizados.


### Infraestrutura:

- Descreva os componentes de infraestrutura do seu projeto, como bancos de dados, APIs externas e outras dependências.
- Explique como a infraestrutura se integra à arquitetura MVC.


### Justifique as escolhas feitas e como elas impactam o projeto.
#### Implicações da Arquitetura:
Descreva as implicações da arquitetura em termos de escalabilidade, manutenção, testabilidade e outros aspectos importantes.

### Recursos Adicionais:
Documentação do Sails.js: https://github.com/balderdashy/sails
Tutorial do draw.io: https://m.youtube.com/watch?v=w3zm-wbmlpc
Exemplos de diagramas MVC: https://www.lucidchart.com/pages/templates
