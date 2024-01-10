# Importar el módulo math para utilizar la función logaritmo
import math
#Jonathan Pozo - 4to nivel
#Propagacion de ondas 
#UTN - Telecomunicaciones

# Definir una función que calcule la atenuación en la transmisión de señal en el vacío
def calcular_atenuacion_transmision(distancia, frecuencia, factor_atenuacion):
  # Aplicar la fórmula de atenuación
  atenuacion = 20 * math.log10(frecuencia) + (10 * factor_atenuacion) * math.log10(distancia) - 147.56
  # Devolver el resultado
  return atenuacion

# Pedir al usuario que ingrese la distancia, la frecuencia y seleccione el tipo de entorno
distancia = float(input("Ingrese la distancia en kilómetros: "))
frecuencia = float(input("Ingrese la frecuencia en MHz: "))
print("Seleccione el tipo de entorno:")
print("1. Espacio Libre")
print("2. Zona urbana")
print("3. Ambiente móvil")
print("4. Línea de visión directa")
print("5. Bloqueo por estructuras edificadas")
print("6. Bloqueo por instalaciones industriales")
tipo_entorno = int(input("Ingrese el número correspondiente al tipo de entorno: "))

# Asignar el valor del factor de atenuación según el tipo de entorno
if tipo_entorno == 1:
  factor_atenuacion = 2
elif tipo_entorno == 2:
  factor_atenuacion = 3.5
elif tipo_entorno == 3:
  factor_atenuacion = 5
elif tipo_entorno == 4:
  factor_atenuacion = 1.8
elif tipo_entorno == 5:
  factor_atenuacion = 6
elif tipo_entorno == 6:
  factor_atenuacion = 3
else:
  print("Opción no válida")
  exit()

# Llamar a la función y mostrar el resultado
atenuacion_transmision = calcular_atenuacion_transmision(distancia, frecuencia, factor_atenuacion)
print(f"La atenuación en la transmisión de señal en el entorno especificado es de {atenuacion_transmision} dB")
