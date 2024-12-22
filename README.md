class Dia:
  def __init__(self, temperatura):
    self.temperatura = temperatura

  def get_temperatura(self):
    return self.temperatura

class Semana:
  def __init__(self):
    self.dias = []

  def agregar_dia(self, dia):
    self.dias.append(dia)

  def calcular_promedio(self):
    temperaturas = [dia.get_temperatura() for dia in self.dias]
    return sum(temperaturas) / len(temperaturas)

# Crear una semana y agregar los días
semana = Semana()
for _ in range(7):
  temperatura = float(input("Ingrese la temperatura del día: "))
  dia = Dia(temperatura)
  semana.agregar_dia(dia)

# Calcular y mostrar el promedio
promedio = semana.calcular_promedio()
print(f"El promedio semanal de temperatura es: {promedio:.2f} °C")
