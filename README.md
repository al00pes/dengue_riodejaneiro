# Análise Epidemiológica da Dengue

Introdução :

A análise de dados epidemiológicos é crucial para o monitoramento e controle de doenças infecciosas, como a dengue. Este projeto visa analisar dados semanais de casos de dengue em diferentes cidades, utilizando um modelo nowcasting. Os dados são consumido atráves da API [info.dengue](http://info.dengue.mat.br/) semanalmente, permitindo uma avaliação detalhada da situação epidemiológica em diferentes localidades.Além disso, o projeto inclui a plotagem de gráficos que mostram a média de casos e a média de casos estimados.

Dicionário dos Dados
Os dados contêm várias colunas importantes, que são descritas a seguir:

- data_iniSE: Primeiro dia da semana epidemiológica (domingo).
- SE: Semana epidemiológica.
- casos_est: Número estimado de casos por semana utilizando o modelo nowcasting (os valores são atualizados retrospectivamente todas as semanas).
- casos_est_min e casos_est_max: Intervalo de credibilidade de 95% do número estimado de casos.
- casos: Número de casos notificados por semana (os valores são atualizados retrospectivamente todas as semanas).
- p_rt1: Probabilidade de (Rt>1). Para emissão do alerta laranja utilizamos o critério p_rt1 > 0,95 por 3 semanas ou mais;
- p_inc100k: Taxa de incidência estimada por 100 mil habitantes.
- Localidade_id: Divisão submunicipal (atualmente implementada apenas no Rio de Janeiro).
- nivel: Nível de alerta (1 = verde, 2 = amarelo, 3 = laranja, 4 = vermelho).
- id: Índice numérico.
- versao_modelo: Versão do modelo (uso interno).
- Rt: Estimativa pontual do número reprodutivo de casos.
- pop: População estimada (IBGE).
- tempmin: Média das temperaturas mínimas diárias ao longo da semana.
- umidmax: Média da umidade relativa do ar máxima diária ao longo da semana.
- receptivo: Indica receptividade climática, ou seja, condições para alta capacidade vetorial. 0 = desfavorável, 1 = favorável, 2 = favorável nesta semana e na semana passada, 3 = favorável durante pelo menos três semanas (suficiente 
 para completar um ciclo de transmissão).
- transmissão: Evidência de transmissão sustentada: 0 = nenhuma evidência, 1 = possível, 2 = provável, 3 = altamente provável.
- nivel_inc: Incidência estimada abaixo do limiar pré-epidêmico, 1 = acima do limiar pré-epidêmico, mas abaixo do limiar epidêmico, 2 = acima do limiar epidêmico.
- notif_accum_year: Número acumulado de casos por ano.

# API DENGUE
As tabelas do Infodengue contêm dados agregados por semana, fornecidos por diferentes fontes. Esses dados podem ser consultados por meio de um formulário ou diretamente do Python, via consulta de uma API. Esta funcionalidade está disponível através da URL:

https://info.dengue.mat.br/api/alertcity?params



  
