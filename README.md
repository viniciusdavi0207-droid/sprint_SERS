# sprint_SERS

Enzo Posterlli Strinta - RM570035
Giovanna Tristão Lopes - RM572552
Vinicius Brito Davi - RM569709

⚡ ChargeGrid Intelligence - Monitoramento Inteligente de Eletroposto
📋 Descrição do Projeto

O ChargeGrid Intelligence é um sistema de monitoramento energético desenvolvido em Python para simular a operação de um eletroposto de recarga para veículos elétricos.

O objetivo do projeto é demonstrar como técnicas simples de análise de dados podem ser utilizadas para:

Monitorar o consumo energético dos carregadores;
Simular geração de energia solar fotovoltaica;
Calcular custos operacionais com tarifa dinâmica;
Gerar alertas automáticos de alto consumo;
Produzir relatórios de desempenho energético;
Visualizar os dados através de gráficos.

O sistema representa uma prova de conceito para aplicações de cidades inteligentes e infraestrutura sustentável de mobilidade elétrica.

🎯 Objetivos
Simular o funcionamento de um eletroposto durante 24 horas.
Registrar consumo energético dos carregadores.
Simular produção de energia solar ao longo do dia.
Calcular a energia adquirida da rede elétrica.
Aplicar tarifas dinâmicas conforme o horário.
Gerar alertas de consumo elevado.
Produzir indicadores de eficiência energética.
Exibir gráficos para análise visual dos dados.

🛠 Tecnologias Utilizadas
O projeto foi desenvolvido utilizando:

Python 3
Pandas
Matplotlib
Random (biblioteca padrão do Python)

📦 Instalação
Clone o repositório:

git clone https://github.com/seu-usuario/chargegrid-intelligence.git

Entre na pasta do projeto:
cd chargegrid-intelligence

Instale as dependências:

pip install pandas matplotlib
▶️ Como Executar

Execute o arquivo Python:

python chargegrid.py

Ou execute diretamente no Google Colab.

⚙️ Funcionamento do Sistema
1. Simulação das Horas do Dia
O sistema gera dados para as 24 horas:

horas = list(range(24))

2. Consumo dos Carregadores
A cada hora é gerado um valor aleatório de consumo:

c = random.randint(40, 120)

Faixa simulada:
Mínimo: 40 kWh
Máximo: 120 kWh

3. Geração Solar
A geração fotovoltaica ocorre apenas durante o dia:

if 6 <= h <= 18:
    s = random.randint(20, 80)
else:
    s = 0

Período de geração:
06h às 18h

Faixa simulada:
20 kWh a 80 kWh

4. Energia Comprada da Rede
Caso a geração solar não seja suficiente:

rede = max(0, c - s)

A energia restante é adquirida da concessionária.

5. Tarifa Dinâmica
O sistema aplica diferentes tarifas:

Horário de Pico
18h às 22h
tarifa = 1.20

Horário Normal
Demais horários
tarifa = 0.75

6. Cálculo do Custo
custo_hora = rede * tarifa

O custo depende da energia comprada da rede e da tarifa vigente.

7. Armazenamento dos Dados
Os dados são organizados em um DataFrame:

dados = pd.DataFrame({
    "Hora": horas,
    "Consumo_kWh": consumo,
    "Solar_kWh": solar,

🚨 Sistema de Alertas
O programa identifica automaticamente horas com consumo elevado:

if consumo[i] > 100:

Exemplo:
⚠️ Hora 8: Consumo elevado (112 kWh)
⚠️ Hora 19: Consumo elevado (118 kWh)
📊 Relatório Energético

Ao final da execução são calculados:

Consumo Total
total_consumo
Energia Solar Gerada
total_solar
Custo Total
total_custo
Percentual de Economia Solar
economia = (total_solar / total_consumo) * 100

Exemplo:
Consumo Total: 1850 kWh
Geração Solar: 620 kWh
Custo Total: R$ 1085.50
Energia suprida pela fonte solar: 33.51%

📈 Visualização Gráfica
O sistema gera um gráfico comparando:

Consumo dos carregadores
Geração de energia solar
plt.plot(horas, consumo)
plt.plot(horas, solar)

O gráfico facilita a análise da eficiência energética ao longo do dia.

🌱 Sustentabilidade
O projeto demonstra conceitos importantes de sustentabilidade:

Uso de energia renovável.
Redução da dependência da rede elétrica.
Monitoramento inteligente de consumo.
Eficiência energética.
Apoio à mobilidade elétrica.
