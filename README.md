> <B>⚠️ Esse README ainda esta sob construção</B>

<h1 align="center">
  <img src="https://raw.githubusercontent.com/CatarinaRRF/IC_design_de_siRNA/main/media/Creative.png" alt="logo">
</h1>

<h3 align="center">siRNA Seeker - Design de siRNA</h3>

<p align="center">
    <a href="">
    <img src="https://img.shields.io/github/last-commit/CatarinaRRF/IC_design_de_siRNA?color=informational&style=flat-square"
         alt="GitHub last commit">
    <a href="https://github.com/CatarinaRRF/Challenge-Alura-Cash-19-08-22">
    <img src= http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=green&style=flat-square >

</p>

<p align="center">
  <a href="#sobre">Sobre</a> •
  <a href="#metodologia">Metodologia</a> •
  <a href="#resultados">Resultados</a> •
  <a href="#conclusão">Conclusão</a> •
  <a href="#arquivos">Arquivos</a> •
  <a href="#creditos">Creditos</a>
  
</p>

# Sobre 
<p align="justify"> A regulação da expressão gênica é um campo crucial da pesquisa científica, envolvendo diversos mecanismos que incluem o uso de pequenas moléculas de RNA, como siRNA e miRNA, para desempenhar um papel fundamental no silenciamento pós-transcricional de genes, conhecido como interferência por RNA (RNAi). A capacidade de utilizar esses tipos de RNA como ferramentas na criação de novas tecnologias tem despertado um interesse significativo entre os cientistas. Nesse contexto, apresentamos este algoritmo, projetado para automatizar o processo de encontrar siRNA, facilitando a pesquisa e o desenvolvimento de novas aplicações no campo da genética e biotecnologia.

<sup>

## Metodologia
<p align="justify"> 
Para automatizar e aprimorar o processo de seleção de siRNA, desenvolvemos um algoritmo com as seguintes etapas:
</p>

<h1 align="center">
  <img src="https://raw.githubusercontent.com/CatarinaRRF/IC_design_de_siRNA/main/media/algoritimo_siRNA.png">
</h1>

📂<B><i>Etapa 1:</i></B> Entrada de Dados
<p align="justify">O algoritmo recebe um arquivo FASTA inserido pelo usuário, contendo sequências de DNA a serem analisadas, onde cada sequência é identificada por um cabeçalho precedido por ">".</p>

📂<B><i>Etapa 2:</i></B> Transcrição das Sequências de DNA
<p align="justify">Para cada sequência de DNA no arquivo FASTA, o algoritmo realiza a transcrição, convertendo-a em uma sequência de RNA complementar.</p>

📂<B><i>Etapa 3:</i></B> Identificação de siRNA
<p align="justify">O algoritmo procura nas sequências de RNA resultantes por potenciais sequências de 22 pb que podem atuar como siRNA.</p>

📂<B><i>Etapa 4:</i></B> Verificação da Qualidade do siRNA
<p align="justify">De acordo com Reynolds et al. (2004), Ui-Tei et al. (2004) e Amarzguioui et al. estabeleceram critérios para determinar a funcionalidade das sequências de siRNA, que incluem o conteúdo de CG%, temperatura de melting e baixa estabilidade interna. Assim, os seguintes criterios seram usados para determinar se uma sequencia sera funcional. Os critérios são classificados em ordem de importância da seguinte forma:

| Rank | Critério                                   | Pontuação |
| ---- | ------------------------------------------ | --------- |
| 1    | Ausência de repetições invertidas (hairpin) | -         |
| 2    | Estabilidade interna baixa                 | -2 a 10   |
| 3    | Baixo teor de GC                           | 0 ou 4    |
| 4    | Posições específicas                       | -4 a 6    |

Assim, os siRNAs candidatos são avaliados de acordo com esses critérios para determinar sua viabilidade. Para o primeiro critério, os siRNAs que não atendem são descartados. Para os demais critérios, é atribuída uma pontuação: 10 pontos para o critério de estabilidade baixa, 4 ponto para o critério de baixo teor GC e 1 ponto para cada posição específicas.

É importante destacar que, no caso das posições específicas, cada posição que corresponde a um nucleotídeo ideal recebe 1 ponto, enquanto a não conformidade com essa posição retorna 0 pontos. Nas posições onde o nucleotídeo precisa ser específico, é deduzido 1 ponto se não estiver em conformidade.

A pontuação então sera trasformada em pencentual, onde apenas as sequencias com mais de 80% de conformidade seram levadas para as proximas fases.</p>

📂<B><i>Etapa 5:</i></B> Exclusão de siRNA que não atendem aos critérios
<p align="justify">Os siRNAs que não atendem aos critérios de qualidade são excluídos da análise subsequente.</p>

📂<B><i>Etapa 6:</i></B> Execução do BLAST
<p align="justify">Para cada siRNA de qualidade, o algoritmo realiza uma busca BLAST em um banco de dados de referência para identificar potenciais alvos no transcriptoma.</p>

📂<B><i>Etapa 7:</i></B> Extração de Informações do BLAST
<p align="justify">Após a execução do BLAST, o algoritmo extrai informações relevantes, incluindo a sequência do alvo, o score do alinhamento e outros parâmetros importantes.</p>

📂<B><i>Etapa 8:</i></B> Criação de Tabela de Resultados
<p align="justify">Com as informações extraídas do BLAST, o algoritmo cria uma tabela de resultados, fornecendo informações sobre a sequência de siRNA, o score do BLAST e os possíveis alvos identificados.</p>

📂<B><i>Etapa 9:</i></B> Fim
<p align="justify">O algoritmo conclui a análise das sequências de DNA, gerando uma tabela de resultados que pode ser utilizada para inferir a função ou alvo dos siRNAs identificados, contribuindo para a pesquisa em biologia molecular e terapia genética.</p>

### Tecnologias usados 
* Python
* Google Colab
* Python libraries: Biopython, Pandas

## Programa



## Inicialização
<p align="justify">Em linhas gerais, constatou-se que <b>Lorem ipsum dolor sit amet</b>. Verifica-se, portanto, <b>consectetur adipiscing elit</b>. Ademais, verifica-se <b>sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</b>.

Cabe destacar ainda que Lorem ipsum dolor sit amet.
</p>

## Arquivos
<img align="right" height="150" src="https://img.freepik.com/vetores-gratis/caixa-de-armazenamento-de-arquivamento-de-arquivos-de-gabinete-de-documentos_33099-829.jpg?w=740&t=st=1662167069~exp=1662167669~hmac=fb6f9c20366de7cfa78155d9e4e0219a230a9affa0fccec9c10875147c2d2c85">

* Dados <i>"Crus"</i> <a href=''>Link</a>
* Dados processados após limpeza de dados <a href=''>Link</a>
* Notebooks da Análise Exploratória de Dados <a href=''>Link</a>
* Notebooks da Modelagem de Dados <a href=''>Link</a>
* Dashboard <a href=''>Link</a>

## Créditos
* UFU patos de minas
* 

<img src="https://github.com/CatarinaRRF/Challenge-Alura-Cash-19-08-22/blob/974dd832c3980dd107a36a4b6906b616bb7b71f2/media/hr_line_redme.png" alt="logo">

<p align="center">
 <a href='https://www.linkedin.com/public-profile'><img src='https://cdn-icons-png.flaticon.com/512/174/174857.png' height=20px></a> <a href='https://www.kaggle.com/ccfreitas'><img src='https://cdn4.iconfinder.com/data/icons/logos-and-brands/512/189_Kaggle_logo_logos-512.png' height=20px></a>
</p>
