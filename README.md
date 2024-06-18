# Simulação de Corrida de Fórmula E

## Descrição do Projeto
Este projeto simula uma corrida de Fórmula E, atribui pontos aos pilotos com base em suas posições finais e exibe
a classificação do campeonato após a corrida. É uma ferramenta útil para visualizar como mudanças aleatórias nas
posições podem afetar a pontuação geral dos pilotos ao longo de uma temporada.

## Requisitos
Para executar este projeto, você precisará de:
- Python 3.x
- Módulo `random` (incluído na biblioteca padrão do Python)

## Instruções de Uso
Siga estas etapas para usar o projeto:
1. Clone o repositório ou copie o código para um arquivo local.
2. Certifique-se de ter o Python 3.x instalado em seu sistema.
3. Execute o arquivo Python com o seguinte comando:

python nome_do_arquivo.py

4. Veja a saída no console para verificar os resultados da corrida e a classificação do campeonato.

## Código do Projeto
O código a seguir implementa a simulação de corrida:

```bash
import random

class Driver:
 def __init__(self, name, team):
     self.name = name
     self.team = team
     self.points = 0

 def add_points(self, points):
     self.points += points
```

# Criando os pilotos
```bash
driver1 = Driver("Antonio Felix da Costa", "TAG HEUER PORSCHE")
```
# (Outros pilotos são criados da mesma forma)
# Lista dos pilotos
```bash
drivers = [driver1, driver2, driver3, ..., driver20]
```
# Simulando a corrida
```bash
def simulate_race():
 results = list(range(1, 21))  # resultado da corrida e como eles foram
 random.shuffle(results)  # deixando os resultados aleatórios
 return results
```
# Pontuação dos corredores em base nos seus números
```bash
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
```
# Simulação da corrida
```bash
race_results = simulate_race()
```
# Pontuação dos pilotos
```bash
assign_points(race_results)
```
# Organizando com a pontuação
```bash
drivers.sort(key=lambda x: x.points, reverse=True)
```
# Tabela no fim da corrida
```bash
print("Formula E Championship Standings after the race:")
print("{:<20} {:<20} {:<10}".format("Driver", "Team", "Points"))
for driver in drivers:
 print("{:<20} {:<20} {:<10}".format(driver.name, driver.team, driver.points))
```
# Explicação do Código
## O código é composto pelas seguintes partes:

### Classe Driver
A classe Driver representa um piloto e contém atributos para o nome, a equipe e os pontos do piloto.
Ela também possui um método para adicionar pontos.
```bash
class Driver:
    def __init__(self, name, team):
        self.name = name
        self.team = team
        self.points = 0

    def add_points(self, points):
        self.points += points
```
# Criação dos Pilotos
Instâncias da classe Driver são criadas para representar cada piloto participante da simulação.
Esses pilotos são armazenados em uma lista chamada drivers.

# Criando os pilotos
```bash
driver1 = Driver("Antonio Felix da Costa", "TAG HEUER PORSCHE")
# (Outros pilotos são criados da mesma forma)
# Lista dos pilotos
drivers = [driver1, driver2, driver3, ..., driver20]
```
# Simulação da Corrida
A função simulate_race embaralha uma lista de posições para simular os resultados de uma corrida.
```bash
def simulate_race():
    results = list(range(1, 21))  # resultado da corrida e como eles foram
    random.shuffle(results)  # deixando os resultados aleatórios
    return results
```
# Atribuição de Pontos
A função assign_points atribui pontos aos pilotos com base em suas posições na corrida. Os pontos
são atribuídos de acordo com a posição final de cada piloto.
```bash
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
```

# Exibição dos Resultados
Os resultados da corrida são simulados, os pontos são atribuídos e os pilotos são ordenados pela pontuação. A
classificação final é exibida no console.

# Simulação da corrida
```bash
race_results = simulate_race()
```
# Pontuação dos pilotos
```bash
assign_points(race_results)
```
# Organizando com a pontuação
```bash
drivers.sort(key=lambda x: x.points, reverse=True)
```
# Tabela no fim da corrida
```bash
print("Formula E Championship Standings after the race:")
print("{:<20} {:<20} {:<10}".format("Driver", "Team", "Points"))
for driver in drivers:
    print("{:<20} {:<20} {:<10}".format(driver.name, driver.team, driver.points))
```
# Dependências
O único módulo necessário para este projeto é o random, que faz parte da biblioteca padrão do Python
e não requer instalação adicional.
