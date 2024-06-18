<html lang="pt-BR">
    <title>README - Simulação de Corrida de Fórmula E</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0 auto;
            padding: 0 2rem;
            max-width: 800px;
        }

        h1,
        h2,
        h3 {
            color: #333;
        }

        code {
            background: #f4f4f4;
            padding: 2px 4px;
            border-radius: 4px;
        }

        pre {
            background: #f4f4f4;
            padding: 1rem;
            border-radius: 4px;
            overflow-x: auto;
        }

        a {
            color: #0366d6;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }
    </style>
</head>

<body>

    <h1>Simulação de Corrida de Fórmula E</h1>

    <h2>Descrição do Projeto</h2>
    <p>Este projeto simula uma corrida de Fórmula E, atribui pontos aos pilotos com base em suas posições finais e exibe
        a classificação do campeonato após a corrida. É uma ferramenta útil para visualizar como mudanças aleatórias nas
        posições podem afetar a pontuação geral dos pilotos ao longo de uma temporada.</p>

    <h2>Requisitos</h2>
    <p>Para executar este projeto, você precisará de:</p>
    <ul>
        <li>Python 3.x</li>
        <li>Módulo <code>random</code> (incluído na biblioteca padrão do Python)</li>
    </ul>

    <h2>Instruções de Uso</h2>
    <p>Siga estas etapas para usar o projeto:</p>
    <ol>
        <li>Clone o repositório ou copie o código para um arquivo local.</li>
        <li>Certifique-se de ter o Python 3.x instalado em seu sistema.</li>
        <li>Execute o arquivo Python com o seguinte comando:
            <pre><code>python nome_do_arquivo.py</code></pre>
        </li>
        <li>Veja a saída no console para verificar os resultados da corrida e a classificação do campeonato.</li>
    </ol>

    <h2>Código do Projeto</h2>
    <p>O código a seguir implementa a simulação de corrida:</p>
    <pre><code>import random

class Driver:
    def __init__(self, name, team):
        self.name = name
        self.team = team
        self.points = 0

    def add_points(self, points):
        self.points += points

# Criando os pilotos
driver1 = Driver("Antonio Felix da Costa", "TAG HEUER PORSCHE")
driver2 = Driver("Nick Cassidy", "JAGUAR TCS RACING")
driver3 = Driver("Oliver Rowland", "NISSAN")
driver4 = Driver("Pascal Werhlein", "TAG HEUER PORSCHE")
driver5 = Driver("Jake Dennis", "ANDRETTI")
driver6 = Driver("Mitch Evans", "JAGUAR TCS RACING")
driver7 = Driver("Jehan Daruvala", "MASERATI MSG RACING")
driver8 = Driver("Taylor Barnard", "NEOM MCLAREN")
driver9 = Driver("Joel Eriksson", "ENVISION RACING")
driver10 = Driver("Jean-Éric Vergne", "DS Techeetah")
driver11 = Driver("Lucas Di-Grassi", "ABT CUPRA")
driver12 = Driver("Jake Hughes", "NEOM MCLAREN")
driver13 = Driver("Sérgio Sette Câmara", "ERT")
driver14 = Driver("Paul Aron", "ENVISION RACING")
driver15 = Driver("Kevin Van Der Linde", "ABT CUPRA")
driver16 = Driver("Edoardo Mortara", "MAHINDRA RACING")
driver17 = Driver("Dan Ticktum", "ERT FORMULA")
driver18 = Driver("Jordan King", "MAHINDRA RACING")
driver19 = Driver("Norman Nato", "ANDRETTI")
driver20 = Driver("Stoffel Vandoorne", "DS PENSKE")

# Lista dos pilotos
drivers = [driver1, driver2, driver3, driver4, driver5, driver6, driver7, driver8, driver9, driver10,
           driver11, driver12, driver13, driver14, driver15, driver16, driver17, driver18, driver19,
           driver20]

# Simulando a corrida
def simulate_race():
    results = list(range(1, 21))  # resultado da corrida e como eles foram
    random.shuffle(results)  # deixando os resultados aleatórios
    return results

# Pontuação dos corredores em base nos seus números
def assign_points(results):
    for position, index in enumerate(results):
        if position == 0:
            drivers[index - 1].add_points(25)  # Primeiro
        elif position == 1:
            drivers[index - 1].add_points(18)  # Segundo
        elif position == 2:
            drivers[index - 1].add_points(15)  # Terceiro
        elif position == 3:
            drivers[index - 1].add_points(12)  # Quarto
        elif position == 4:
            drivers[index - 1].add_points(10)  # Quinto
        elif position == 5:
            drivers[index - 1].add_points(8)  # Sexto
        elif position == 6:
            drivers[index - 1].add_points(6)  # Sétimo
        elif position == 7:
            drivers[index - 1].add_points(4)  # Oitavo
        elif position == 8:
            drivers[index - 1].add_points(2)  # Nono
        elif position == 9:
            drivers[index - 1].add_points(1)  # Décimo
        else:
            drivers[index - 1].add_points(0)  # Demais posições

# Simulação da corrida
race_results = simulate_race()

# Pontuação dos pilotos
assign_points(race_results)

# Organizando com a pontuação
drivers.sort(key=lambda x: x.points, reverse=True)

# Tabela no fim da corrida
print("Formula E Championship Standings after the race:")
print("{:<20} {:<20} {:<10}".format("Driver", "Team", "Points"))
for driver in drivers:
    print("{:<20} {:<20} {:<10}".format(driver.name, driver.team, driver.points))
</code></pre>

    <h2>Explicação do Código</h2>
    <p>O código é composto pelas seguintes partes:</p>

    <h3>Classe <code>Driver</code></h3>
    <p>A classe <code>Driver</code> representa um piloto e contém atributos para o nome, a equipe e os pontos do piloto.
        Ela também possui um método para adicionar pontos.</p>
    <pre><code>class Driver:
    def __init__(self, name, team):
        self.name = name
        self.team = team
        self.points = 0

    def add_points(self, points):
        self.points += points
</code></pre>

    <h3>Criação dos Pilotos</h3>
    <p>Instâncias da classe <code>Driver</code> são criadas para representar cada piloto participante da simulação.
        Esses pilotos são armazenados em uma lista chamada <code>drivers</code>.</p>
    <pre><code># Criando os pilotos
driver1 = Driver("Antonio Felix da Costa", "TAG HEUER PORSCHE")
# (Outros pilotos são criados da mesma forma)
# Lista dos pilotos
drivers = [driver1, driver2, driver3, ..., driver20]
</code></pre>

    <h3>Simulação da Corrida</h3>
    <p>A função <code>simulate_race</code> embaralha uma lista de posições para simular os resultados de uma corrida.
    </p>
    <pre><code>def simulate_race():
    results = list(range(1, 21))  # resultado da corrida e como eles foram
    random.shuffle(results)  # deixando os resultados aleatórios
    return results
</code></pre>

    <h3>Atribuição de Pontos</h3>
    <p>A função <code>assign_points</code> atribui pontos aos pilotos com base em suas posições na corrida. Os pontos
        são atribuídos de acordo com a posição final de cada piloto.</p>
    <pre><code>def assign_points(results):
    for position, index in enumerate(results):
        if position == 0:
            drivers[index - 1].add_points(25)  # Primeiro
        elif position == 1:
            drivers[index - 1].add_points(18)  # Segundo
        elif position == 2:
            drivers[index - 1].add_points(15)  # Terceiro
        elif position == 3:
            drivers[index - 1].add_points(12)  # Quarto
        elif position == 4:
            drivers[index - 1].add_points(10)  # Quinto
        elif position == 5:
            drivers[index - 1].add_points(8)  # Sexto
        elif position == 6:
            drivers[index - 1].add_points(6)  # Sétimo
        elif position == 7:
            drivers[index - 1].add_points(4)  # Oitavo
        elif position == 8:
            drivers[index - 1].add_points(2)  # Nono
        elif position == 9:
            drivers[index - 1].add_points(1)  # Décimo
        else:
            drivers[index - 1].add_points(0)  # Demais posições
</code></pre>

    <h3>Exibição dos Resultados</h3>
    <p>Os resultados da corrida são simulados, os pontos são atribuídos e os pilotos são ordenados pela pontuação. A
        classificação final é exibida no console.</p>
    <pre><code># Simulação da corrida
race_results = simulate_race()

# Pontuação dos pilotos
assign_points(race_results)

# Organizando com a pontuação
drivers.sort(key=lambda x: x.points, reverse=True)

# Tabela no fim da corrida
print("Formula E Championship Standings after the race:")
print("{:<20} {:<20} {:<10}".format("Driver", "Team", "Points"))
for driver in drivers:
    print("{:<20} {:<20} {:<10}".format(driver.name, driver.team, driver.points))
</code></pre>

    <h2>Dependências</h2>
    <p>O único módulo necessário para este projeto é o <code>random</code>, que faz parte da biblioteca padrão do Python
        e não requer instalação adicional.</p>

    <h2>Contribuições</h2>
    <p>Contribuições para este projeto são bem-vindas. Sinta-se à vontade para abrir um pull request ou enviar sugestões
        para melhorias.</p>

</body>

</html>