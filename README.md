# 😎 Simulación 2 - MLFQ Scheduler Simulation Activity Report

|Who are we?|Contact us|Github|
|---|---|---|
|Valentina Muñoz Rincón 🐜|valentina.munozr1@udea.edu.co|ValenMR|
|Juan Felipe Escobar Rendón 🐔|juan.escobar15@udea.edu.co|juanfes517|

## 🖍 Exercise statement

This program, [mlfq.py](mlfq.py), allows you to see how the MLFQ scheduler presented in this chapter behaves. See the [README](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/cpu-sched-mlfq/README.md) for details.


#### ➡ Ejecute algunos problemas generados aleatoriamente con solo dos trabajos y dos colas. 
#### ➡ Calcule el seguimiento de ejecución de MLFQ para cada uno. 
#### ➡ Simplifique su trabajo limitando la duración de cada trabajo y desactivando las E/S.


## ❓Questions

#### Ⅰ. ¿Cómo ejecutarías el programador para reproducir cada uno de los ejemplos del capítulo?
   
   <details>
   <summary>
      LOOK AT ME!⬇
   </summary>
      
   Comando ejecutado:
      
   ```bash
   python3 mlfq.py -n 2 -M 10 -j 2 -Q "5,3"
   ```
   - `-n 2`: `2` colas en el MLFQ
   - `-M 10`: tiempo máxima de ejecución en 10 unidades de tiempo
   - `-j 2`: Define dos trabajos
   - `-Q "5,3"`: quantum para las dos colas (la primera con más prioridad de `5` unidades de tiempo y la segunda con menos prioridad de `3` unidades de tiempo)     


   #### Terminal:
   
   ![Image 1](ejercicio_1.png)

   Ambos trabajos comienzan simultáneamente, pero debido a sus diferentes tiempos de ejecución y frecuencias de I/O, tienen trayectorias de ejecución distintas. El trabajo `0` tardará más tiempo debido a su mayor `runTime`, pero ambos están sujetos a interupciones por I/O y por las colas de prioridad.


   </details>
   <br>

#### Ⅱ. ¿Cómo configurarías los parámetros del programador para que se comporten como un programador round-robin?

   <details>
   <summary>
       LOOK AT ME!⬇   
   </summary>
   
   > **Recordemos algo** : El RR es un algoritmo de planificación de CPU que proporciona un quantum fijo a cada proceso.

   Comando ejecutado:
      
   ```bash
   python3 mlfq.py -n 1 -Q "5"
   ```

   - `-n 1`: Solo una cola, lo que utiliza RR.
   - `-Q "5"`: 5 unidades de tiempo para todos los trabajos.

   #### Terminal:
   
   ![Image 2](ejercicio_2.png)

   Dado que se configuró con una sola cola el algoritmo se comporta como un Round-Robin. Cada trabajo obtiene 5 unidades de tiempo en orden; si un trabajo no termina en su tiempo (5 unidades), se interrumpe y pasa al final de la cola, así se asgura que cada uno tenga su "turno" para una ejecución más justa y así al final se todos los trabajos se habrán completado. 

   
   </details>
   <br>

4. Craft a workload with two jobs and scheduler parameters so that one job takes advantage of the older Rules 4a and 4b (turned on
with the -S flag) to game the scheduler and obtain 99% of the CPU over a particular time interval.

   <details>
   <summary>Answer</summary>
   Coloque aqui su respuerta
   </details>
   <br>

5. Given a system with a quantum length of 10 ms in its highest queue, how often would you have to boost jobs back to the highest priority level (with the `-B` flag) in order to guarantee that a single longrunning (and potentially-starving) job gets at least 5% of the CPU?

   <details>
   <summary>Answer</summary>
   Coloque aqui su respuerta
   </details>
   <br>

6. One question that arises in scheduling is which end of a queue to add a job that just finished I/O; the -I flag changes this behavior
for this scheduling simulator. Play around with some workloads and see if you can see the effect of this flag.

   <details>
   <summary>Answer</summary>
   Coloque aqui su respuerta
   </details>
   <br>

## Conclusions

Coloque aqui las conclusiones...


### Criterios de evaluación
- [x] Despligue de los resultados y analisis claro de los resultados respecto a lo visto en la teoria.
- [x] Creatividad y orden.
- [x] Sección con las conclusiones de los experimentos realizados.
