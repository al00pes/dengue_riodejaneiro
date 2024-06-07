
# Análise Epidemiológica da Dengue

Este projeto visa analisar dados semanais de casos de dengue em diferentes cidades, utilizando um modelo nowcasting. Os dados são fornecidos por várias fontes e agregados semanalmente, permitindo uma avaliação detalhada da situação epidemiológica em diferentes localidades. Além disso, o projeto inclui a plotagem de gráficos que mostram a média de casos e a média de casos estimados.

## Dicionário dos Dados

Os dados contêm várias colunas importantes, que são descritas a seguir:

- **data_iniSE**: Primeiro dia da semana epidemiológica (domingo).
- **SE**: Semana epidemiológica.
- **casos_est**: Número estimado de casos por semana utilizando o modelo nowcasting (os valores são atualizados retrospectivamente todas as semanas).
- **casos_est_min** e **casos_est_max**: Intervalo de credibilidade de 95% do número estimado de casos.
- **casos**: Número de casos notificados por semana (os valores são atualizados retrospectivamente todas as semanas).
- **p_rt1**: Probabilidade de \(Rt > 1\). Para emissão do alerta laranja, utilizamos o critério \(p\_rt1 > 0,95\) por três semanas ou mais.
- **p_inc100k**: Taxa de incidência estimada por 100 mil habitantes.
- **Localidade_id**: Divisão submunicipal (atualmente implementada apenas no Rio de Janeiro).
- **nivel**: Nível de alerta (1 = verde, 2 = amarelo, 3 = laranja, 4 = vermelho).
- **id**: Índice numérico.
- **versao_modelo**: Versão do modelo (uso interno).
- **Rt**: Estimativa pontual do número reprodutivo de casos.
- **pop**: População estimada (IBGE).
- **tempmin**: Média das temperaturas mínimas diárias ao longo da semana.
- **umidmax**: Média da umidade relativa do ar máxima diária ao longo da semana.
- **receptivo**: Indica receptividade climática, ou seja, condições para alta capacidade vetorial. 0 = desfavorável, 1 = favorável, 2 = favorável nesta semana e na semana passada, 3 = favorável durante pelo menos três semanas (suficiente para completar um ciclo de transmissão).
- **transmissão**: Evidência de transmissão sustentada: 0 = nenhuma evidência, 1 = possível, 2 = provável, 3 = altamente provável.
- **nivel_inc**: Incidência estimada abaixo do limiar pré-epidêmico, 1 = acima do limiar pré-epidêmico, mas abaixo do limiar epidêmico, 2 = acima do limiar epidêmico.
- **notif_accum_year**: Número acumulado de casos por ano.

## API DENGUE

As tabelas do Infodengue contêm dados agregados por semana, fornecidos por diferentes fontes. Esses dados podem ser consultados por meio de um formulário ou diretamente do Python, via consulta de uma API. Esta funcionalidade está disponível através da URL:

```
https://info.dengue.mat.br/api/alertcity?params
```

### Parâmetros Necessários para a API

- **geocode**: Código IBGE da cidade.
- **disease**: Tipo de doença a ser consultada (`str:dengue|chikungunya|zika`).
- **format**: Extensão/formato do arquivo (`str:json|csv`).
- **ew_start**: Semana epidemiológica inicial da consulta (`int:1-53`).
- **ew_end**: Semana epidemiológica final da consulta (`int:1-53`).
- **ey_start**: Ano inicial da consulta (`int:0-9999`).
- **ey_end**: Ano final da consulta (`int:0-9999`).

## Plotagem de Gráficos

Este projeto inclui a plotagem de gráficos que mostram:

- A média dos casos notificados.
- A média dos casos estimados.

Os gráficos ajudam a visualizar a tendência dos casos ao longo do tempo, facilitando a identificação de padrões e a tomada de decisões.

## Como Usar

1. Clone este repositório:
   ```sh
   git clone https://github.com/al00pes/dengue_riodejaneiro.git
   ```
2. Instale as dependências necessárias:
   ```sh
   pip install -r requirements.txt
   ```
3. Execute o script principal para gerar os gráficos:
   ```sh
   python main.py
   ```

## Contribuição

Sinta-se à vontade para contribuir com este projeto. Você pode abrir uma issue para relatar bugs ou solicitar novas funcionalidades, e enviar pull requests para contribuir com o código.

## Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

Esse README fornece uma visão geral clara do projeto, explica os dados e a API utilizada, descreve as funcionalidades de plotagem de gráficos, e inclui instruções sobre como usar o projeto e contribuir para ele.



  
