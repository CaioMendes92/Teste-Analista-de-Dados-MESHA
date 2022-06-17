# Teste Analista de Dados
Critérios avaliadas:
- Uso de Funções DAX
- Documentação das medidas
- ETL
- Modelagem dimensional dos dados

### Desejáveis
- Esquema Estrela
- Criação de visuais com indicadores além dos requisitados.
- SQL (Caso deseje modelar os dados em algum banco)


### Steps:

1. Realizar um Fork desse projeto
2. Realizar a modelagem dimensional da base (Pode ser dentro do próprio PowerBI ou outra ferramenta de ETL)
    - A base está disponível para download [clicando aqui](https://download.inep.gov.br/microdados/microdados_enem_2020.zip).
    - Após descompactar a paste, o Arquivo com a base encontra-se no diretório microdados_enem_2020/DADOS/MICRODADOS_ENEM_2020.csv
    - A documentação necessária sobre os campos da base está disponível nos demais diretórios dentro da pasta descompactada.
4. Disponibilizar o link do seu repositório para posterior avaliação


### Levantar Indicadores
#### Responder às seguintes perguntas:
1. Qual a escola com a maior média de notas?
2. Qual o aluno com a maior média de notas e o valor dessa média?
3. Qual a média geral?
4. Qual o % de Ausentes?
5. Qual o número total de Inscritos?
6. Qual a média por disciplina?
7. Qual a média por Sexo?
8. Qual a média por Etnia?
-----------------------------------------------------------------------------------------------------------
# Considerações Iniciais
Com o intuito de explorar e analisar os dados do enem 2020, foi construído um dashboard utilizando a ferramenta PowerBI. A base de dados se encontra disponível dentro do site: https://download.inep.gov.br/microdados/microdados_enem_2020.zip. 
**O link para o dashboard se encontra [aqui](https://drive.google.com/file/d/1IKEIhqF-SCrbyr_GmkF84f67yKwdCry3/view?usp=sharing)**

# Funções DAX
Algumas funções foram construídas para auxiliar a construção de visualizações. No intuito de facilitar a entendimento, os nomes utilizados são intuitivos, entretanto, para não restar dúvidas, irei explicar cada uma das funções construídas.

- Total de Alunos: Número total de alunos cadastrado para realizar o ENEM no ano de 2020, independente de ter feito a prova ou não.
- Total Faltantes: Número total de alunos que faltaram ao ENEM.
- Media das Notas: Cálculo com a média geral das notas. 
- Media Redação: Cálculo com a média das notas em redação.
- % Redacoes Anuladas: Percentual de redações que foram anuladas.
- % Faltante: Porcentagem de candidatos que faltaram ao enem.

# Visualizações 
Para uma melhor visualização e otimização do dashboard, foi criado uma página para cada parte dos dados.

- Capa: capa do projeto
- Índice: índice com o caminho para ir direto para a área de interesse do dashboard
- Dados do Candidato: resumo dos dados do candidato, o total de candidato, média das notas em geral, por sexo e por área (Ciências Humanas, Ciências da Natureza, Linguagens e Códigos, Matemática) e por cor da prova. Além disso, é possível filtrar por UF, Município e/ou cor/raça.
- Candidatos Faltante: resumo sobre os dados dos candidatos faltantes. O total, sua porcentagem, o total por sexo e por cor/raça. Podendo filtrar por UF, Município e/ou cor/raça
- Top Candidatos: Os 100 primeiros candidatos, ranqueado pela media das notas. É possível filtrar por UF, Município, Sexo e/ou cor/raça.
- Redação: Dados referente a redação, com total de redações aprovadas sem problemas, porcentagem de redações anuladas, contagem de redações por status (fugiu do tema, cópia do texto motivador, texto insuficiente, parte desconectada, não atendimento ao tipo textual ou anulada). Além de uma listagem com todas as notas acima de 950 (na média) e a nota de cada competência. Podendo ser filtrado por UF, Município, Sexo e/ou cor/raça.
- Dados socioeconômicos: Total de resposta por sexo e a média das notas por resposta da questão. Podendo filtrar as respostas do questionário por UF, Municipio e/ou cor/raça.

# Respostas

1. Qual a escola com a maior média de notas?
A partir do ano de 2020, o Inep decidiu retirar o nome das escolas, alegando ferir a LGPD. 
Fonte: https://g1.globo.com/educacao/noticia/2022/02/22/inep-divulga-microdados-do-enem-2020-sem-informacoes-sobre-escola-e-municipio-dos-participantes-especialistas-criticam.ghtml

2. Qual o aluno com a maior média de notas e o valor dessa média?
O aluno com a maior média de notas foi o "200005996961", cuja média foi de 858,58 pontos. Uma análise mais aprofundada, levando em conta a nota de cada uma das áreas pode ser encontrada na página "Top Candidatos". Podendo ver os melhores candidatos por região.

3. Qual a média geral?
A média geral foi de 523,87, sendo a média do sexo masculino de 532 pontos e do sexo feminino de 519. Para uma análise de média por uma região específica ou por cor da prova, ir em "Dados do Candidato".

4. Qual o % de Ausentes?
A porcentagem de faltantes foi de 55,06%, o que dá um total de 3.184.243 candidatos. Vale salientar que, segundo noticiado pela mídia, o total foi de 55,3%. Como uma perspectiva futura eu iria entender mais a fundo o que houve para a porcentagem dar diferente. Para outras análises, como o total de faltantes por município, ir em "Candidatos Faltantes"
fonte: https://guiadoestudante.abril.com.br/enem/enem-2020-acumula-recordes-de-abstencoes/

Qual o número total de Inscritos?
O total foi de 5.783.109, sendo 2.314.304 do sexo masculino e 3.468.805 do sexo feminino.

Qual a média por disciplina?
Ciências da Natureza: 490
Ciências Humanas: 511
Linguagens e Códigos: 524
Matemática: 521

Qual a média por Sexo?
Masculino: 531,70   
Feminino: 518,74

Qual a média por Etnia?
Amarela: 522,11
Branca: 553,84
Indígena: 470,65
Não informado: 530,56
Parda: 506,07
Preta: 498,37

# Questões Técnicas
- Afim de tentar otimizar o processo de utilização, além de diminuir o tamanho do arquivo, as variáveis que não foram utilizadas foram deletadas, conseguindo assim reduzir o tamanho do arquivo em até 3x.
- Além disso, foi feito uma tentativa de utilizar Python para o processo de mudança de nomenclatura de código para os nomes reais, além de resolver a questão de dados faltantes e variáveis com tipos errados. Além disso, foi dividido os dados em várias tabelas, de forma a construir um esquema estrela, entretanto, as mudanças causaram um aumento significativo no tamanho dos dados, saindo de 2gb para 10gb. Acredito que a mudança de código para nome seja o responsável por este aumento. Devido a este problema, a estratégia de usar python foi esquecida, sendo utilizado o próprio PowerBI para renomear os campos.
- Uma possível solução para o futuro seria aprimorar o script em python para o PowerBI já receber os dados tratatos.

# Perspectivas Futuras
- Aprimorar o script em Python na construção do esquema estrela e subir em um banco de dados relacional. Possivelmente resolveria o problema de tamanho e diminuiria o tempo de atualização.
- Criar novas páginas com os campos não utilizados.
- Relacionar dados socioeconomicos com outras variáveis, como a quantidade de faltantes ou então com as notas em redação.
- Melhoras os incones utilizados no dashboard para ficar mais bonito.
