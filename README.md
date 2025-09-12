# atividade-de-sexta
#calcule a força elétrica entre duas cargas pontuais usando a Lei de Coulomb
args:
q1: Magnitude de primeira carga(em Coulomb)
q2: Magnitude da segunda carga(em Coulombs)
r: Distância entre as cargas (em metros)

returns:
A força elétrica entre as cargas(em newtons) retorna um valor positivo
força repulsiva e negativa para força atrativa
import numpy as np
import matplotlib.pyplot as plt

def coulomb_force(q1, q2, r):
    k = 8.98755e9 #constante de Coulomb (N * m^2 / c^2)
    force = k * (q1 * q2) / (r**2)
    return force

#exemplo de uso
carga1 = 1e-6 #1microcoulomb
carga2 = -2e-6 #microcoulombs
distancia = 0.1 # 10 centimetros
forca_eletrica = coulomb_force(carga1, carga2, distancia)
print(f"A força eletrica entre as cargas é: {forca_eletrica:.2f} N")
distancias = np.linspace(0.01, 1, 100)

forcas = []
for distancia in distancias:
  forca = coulomb_force(carga1, carga2, distancia)
  forcas.append(forca)
  
forcas = np.array(forcas)

plt.figure(figsize=(10, 6))
plt.plot(distancias, forcas)
plt.xlabel("Distancia (m)")
plt.ylabel("Forca eletrica (N)")
plt.title("Forca eletrica vs. Distância")
plt.grid(True)
plt.show()

#vai mostrar um grafico
