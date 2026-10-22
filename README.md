# 5azul-francesco-cannella
Pensamiento computacional 
pregunta 1
El patrón que yo vi es que la cantidad de arepas dependiendo de la cantidad para cantidad se va a multiplicar por cierto número y así sucesivamente.
Cuando aumenta la cantidad de arepas, disminuye el número que va a ser multiplicado. Aquí el ejemplo con la lista que puso el prof 
pregunta 2 
P=n(11-n)
pregunta 3
P=10(11-10)
P=(10)1
P=10 bs
pregunta 4
P=
n. 10
x100 = % de desconto
n- (ll-n)

refelixi
https://www.tinkercad.com/things/eoqZjDptuKu-incredible-kup-hango/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=qs5TLU41_e057dGEnJzimKzCBgzKqnBbZIODge3nvhY
<img width="1420" height="1157" alt="image" src="https://github.com/user-attachments/assets/784c4c9d-a618-42b9-a10e-9b0d56592b4d" />
<img width="1420" height="1157" alt="image" src="https://github.com/user-attachments/assets/6b0b6dcb-a934-4c5d-86dc-8dc799365dd8" />
actividad 22/11
1. Descomposición del problema en subproblemas:
 Llegada de estudiantes: Registrar la hora de llegada del alumno al centro de atención.  
 Registro de datos: Capturar el documento de identidad, el tipo de trámite solicitado y si presenta alguna condición de prioridad.  
 Gestión de prioridades: Clasificar al estudiante en la cola preferencial o en la cola regular según la urgencia y duración del trámite.  
 Atención en ventanilla: Llamar al siguiente estudiante disponible y procesar su solicitud.  
 Cierre: Finalizar la gestión, registrar la hora de salida y liberar la ventanilla para la siguiente persona.

2. Datos necesarios para representar a cada estudiante
Para que el algoritmo pueda gestionar correctamente a cada persona, definimos una estructura de datos (o registro) con los siguientes campos:  
 ⁠ID_Estudiante⁠ (Texto/Número): Identificación única del alumno.  
 ⁠Tipo_Tramite⁠ (Texto): Tipo de gestión (⁠Entrega⁠, ⁠Constancia⁠, ⁠Consulta⁠).  
 ⁠Es_Prioritario⁠ (Booleano): ⁠Verdadero⁠ si aplica algún caso prioritario (discapacidad, emergencia, etc.), ⁠Falso⁠ si no.  
 ⁠Tiempo_Estimado⁠ (Número): Duración en minutos aproximada de la atención según el trámite.  
 ⁠Hora_Llegada⁠ (Tiempo): Momento en que el estudiante ingresa al sistema.  
 ⁠Nivel_Prioridad⁠ (Número): Valor calculado para determinar el orden de atención.

3.  Llegada y registro:
Para cada
estudiante que llega Hacer
Leer ID_Estudiante, Tipo_Tramite, Es_Prioritario, Hora_Llegada
Según Tipo_Tramite Hacer
"Solicitud de
"Entrega de
constancia": Tiempo_Estimado
<- 2
documentos":
"Consulta general"':
Tiempo_Estimado <- 5
Tiempo_Estimado
<- 10
FinSegun
Si Es_Prioritario
== Verdadero Entonces
Insertar_Al_Final (ColaPrioritaria, Estudiante)
Sino
Insertar_Por_Tiempo_Menor(ColaGeneral, Estudiante)
FinSi
FinPara
// Atención y Cierre
Mientras ColaPrioritaria NO vacía O ColaGeneral NO vacía Hacer
Si ColaPrioritaria NO vacía Entonces
EstudianteActual <- Extraer_Primero(ColaPrioritaria)
Sino
EstudianteActual <- Extraer_Primero(ColaGeneral)
FinSi
Atender (EstudianteActual, EstudianteActual.Tiempo_Estimado)
Registrar_Cierre (EstudianteActual)
 

4. Criterio de prioridad utilizado y justificación:
Se utiliza un criterio mixto con prioridad preferencial absoluta y ordenamiento por tiempo de trámite más corto (Shortest Job First):  
 Casos prioritarios: Se atienden primero de forma obligatoria por excepción.  
 Cola general: Se da preferencia a los trámites que toman menos tiempo (como la entrega de constancias frente a consultas generales).  
Por qué: Al procesar primero las solicitudes más rápidas, la cantidad de personas esperando disminuye a mayor velocidad, lo que reduce de forma óptima el tiempo promedio de espera global de la fila sin dejar de atender a nadie.
 
Tarea #2

1. Representación de las paradas y distancias:
 Tramo 1: Colegio a Parada 1 (Distancia: 2 km / Estudiantes: 4)
 Tramo 2: Parada 1 a Parada 2 (Distancia: 3 km / Estudiantes: 6)
 Tramo 3: Parada 2 a Parada 3 (Distancia: 2.5 km / Estudiantes: 3)
 Tramo 4: Parada 3 a Parada 4 (Distancia: 4 km / Estudiantes: 5)
 Tramo 5: Parada 4 a Parada 5 (Distancia: 2 km / Estudiantes: 2)
 Tramo 6: Parada 5 a Parada 6 (Distancia: 3 km / Estudiantes: 4)
 Tramo Final: Parada 6 al Colegio (Distancia: 5 km)

2. Algoritmo paso a paso para construir la ruta:
1. Inicio: Partir desde el Colegio hacia la primera parada no visitada más cercana.  
2. Selección: Identificar la parada pendiente que presente la menor distancia desde la posición actual.  
3. Recogida: Ir a esa parada y recoger a los estudiantes.  
4. Registro: Marcar la parada como "Visitada".  
5. Repetición: Repetir los pasos 2 a 4 hasta completar las 6 paradas.  
6. Retorno: Volver al Colegio con todos los estudiantes recogidos.  

3. Ruta propuesta y aplicación del algoritmo:
 Ruta: Colegio -> Parada 1 -> Parada 2 -> Parada 3 -> Parada 4 -> Parada 5 -> Parada 6 -> Colegio.  
 Distancia total: 2 + 3 + 2.5 + 4 + 2 + 3 + 5 = 21.5 km.  
 Total de estudiantes recogidos: 4 + 6 + 3 + 5 + 2 + 4 = 24 estudiantes. 
 
4. Comparación con ruta alternativa y explicación:
 Ruta Propuesta (Secuencial por cercanía): Recorre 21.5 km visitando las 6 paradas de forma progresiva desde el punto de partida.  
 Ruta Alternativa (Inversa: Parada 6 a Parada 1): Obliga al autobús a realizar un primer trayecto largo de 5 km directo hasta la Parada 6 y luego regresar recorriendo las demás paradas.  
 Conclusión: La Ruta Propuesta es mejor bajo el criterio de menor distancia y tiempo en tránsito. Evita recorridos vacíos iniciales muy largos y garantiza que el promedio de tiempo acumulado que pasa cada estudiante dentro del autobús sea menor. 

Tarea #3

1. Descomposición del problema en subproblemas:
 Llegada de estudiantes: Registrar la hora de llegada del alumno al centro de atención.
 Registro de datos: Capturar el documento de identidad, el tipo de trámite solicitado y si presenta alguna condición de prioridad.
 Gestión de prioridades: Clasificar al estudiante en la cola preferencial o en la cola regular según la urgencia y duración del trámite.
 Atención en ventanilla: Llamar al siguiente estudiante disponible y procesar su solicitud.
 Cierre: Finalizar la gestión, registrar la hora de salida y liberar la ventanilla para la siguiente persona.
2. Datos necesarios para representar a cada estudiante:
 ⁠ID_Estudiante⁠ (Texto): Cédula o carnet de identificación.
 ⁠Tipo_Tramite⁠ (Texto): "Entrega de documentos", "Solicitud de constancia" o "Consulta general".
 ⁠Es_Prioritario⁠ (Booleano): Verdadero si aplica caso prioritario; Falso si no.
 ⁠Tiempo_Estimado⁠ (Entero): Duración en minutos según el tipo de trámite.
 ⁠Hora_Llegada⁠ (Hora): Hora exacta de ingreso a la fila.

Llegada y registro
Para cada
estudiante
que llega
Hacer
Leer ID_Estudiante, Tipo_Tramite, Es_Prioritario, Hora_Llegada
Según Tipo_Tramite Hacer
"Solicitud de
constancia": Tiempo_Estimado <- 2
"Entrega de documentos":
"Consulta general":
Tiempo_Estimado
<- 5
FinSegún
Tiempo_Estimado <- 10
Si Es_Prioritario == Verdadero
Entonces
Insertar_Al_Final (ColaPrioritaria, Estudiante)
Sino
Insertar_Por_Tiempo_Menor(ColaGeneral, Estudiante)
FinSi
FinPara
// Atención y
Mientras ColaPrioritaria NO vacía O ColaGeneral NO
vacía Hacer
Si ColaPrioritaria
NO vacía
Entonces
EstudianteActual <- Extraer_Primero(ColaPrioritaria)
Sino
EstudianteActual <- Extraer_Primero(ColaGeneral)
FinSi
Atender (EstudianteActual, EstudianteActual.Tiempo_Estimado)
Registrar_Cierre(EstudianteActual)
FinMientras

2. 1. Representación de las paradas y distancias:
 Tramo 1: Colegio a Parada 1 (Distancia: 2 km / Estudiantes: 4)
 Tramo 2: Parada 1 a Parada 2 (Distancia: 3 km / Estudiantes: 6)
 Tramo 3: Parada 2 a Parada 3 (Distancia: 2.5 km / Estudiantes: 3)
 Tramo 4: Parada 3 a Parada 4 (Distancia: 4 km / Estudiantes: 5)
 Tramo 5: Parada 4 a Parada 5 (Distancia: 2 km / Estudiantes: 2)
 Tramo 6: Parada 5 a Parada 6 (Distancia: 3 km / Estudiantes: 4)
 Tramo Final: Parada 6 al Colegio (Distancia: 5 km)
2. Algoritmo paso a paso para construir la ruta:
1. Inicio: Partir desde el Colegio hacia la primera parada no visitada más cercana.
2. Selección: Identificar la parada pendiente que presente la menor distancia desde la posición actual.
3. Recogida: Ir a esa parada y recoger a los estudiantes.
4. Registro: Marcar la parada como "Visitada".
5. Repetición: Repetir los pasos 2 a 4 hasta completar las 6 paradas.
6. Retorno: Volver al Colegio con todos los estudiantes recogidos.
3. Ruta propuesta y aplicación del algoritmo:
 Ruta: Colegio -> Parada 1 -> Parada 2 -> Parada 3 -> Parada 4 -> Parada 5 -> Parada 6 -> Colegio.
 Distancia total: 2 + 3 + 2.5 + 4 + 2 + 3 + 5 = 21.5 km.
 Total de estudiantes recogidos: 4 + 6 + 3 + 5 + 2 + 4 = 24 estudiantes.
4. Comparación con ruta alternativa y explicación:
 Ruta Propuesta (Secuencial por cercanía): Recorre 21.5 km visitando las 6 paradas de forma progresiva desde el punto de partida.
2.  Ruta Alternativa (Inversa: Parada 6 a Parada 1): Obliga al autobús a realizar un primer trayecto largo de 5 km directo hasta la Parada 6 y luego regresar recorriendo las demás paradas.
3.  Conclusión: La Ruta Propuesta es mejor bajo el criterio de menor distancia y tiempo en tránsito. Evita recorridos vacíos iniciales muy largos y garantiza que el promedio de tiempo acumulado que pasa cada estudiante dentro del autobús sea menor.

4. Tarea 

Inicio
Leer notal, nota2, nota3
// Validación para que las notas
Si (notal ›= 0 Y nota1
estén entre 0 y 100
<= 100) Y (nota2 ›= 0 Y nota2 <= 100) Y (nota3
>= 0 Y nota3 <= 100]
promedio = (notal + nota2 + nota3) / 3
Escribir "El promedio obtenido es: ", promedio
Si promedio ›= 60 Entonces
Escribir "Resultado: Aprueba"
Sino Si promedio ›= 50 Entonces
Escribir "Resultado: Debe ir a recuperación"
SiNo
Escribir "Resultado: No aprueba"
FinSi
SiNo
Escribir "Error: Una o más notas ingresadas no
son válidas (deben
estar entre 6 y 100,
FinSi
