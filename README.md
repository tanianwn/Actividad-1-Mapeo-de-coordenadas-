# Actividad-1-Mapeo-de-coordenadas

### 1. Sistema de Referencia Inercial (El Global o "El Mundo")
* **¿Qué es?:** Es el mapa fijo y absoluto. Imagina una cuadrícula dibujada en el piso de un cuarto que **nunca se mueve**. 
* **En el código:** Son las coordenadas iniciales de la tabla de datos (por ejemplo, `x = -5, y = 9`). Representan en qué punto exacto de ese cuarto global está estacionado el robot.



### 2. Sistema de Referencia Local (El del Robot)
* **¿Qué es?:** Es la perspectiva "en primera persona" del robot. El marco está "pegado" a su chasis. Para el robot, él siempre es su propio centro (origen `0,0`) y su "frente" siempre es su eje X, sin importar hacia dónde esté apuntando dentro del cuarto.
* **En el código:** Es el vector resultante que se guarda en la variable `xi_local_1`.

---

### 3. Resumen del Mapeo (El objetivo del algoritmo)
El programa funciona como un "traductor" espacial bidireccional: 
1. **Punto de partida:** Toma la posición del robot en el mundo fijo (**Inercial**).
2. **Transformación Directa:** Le aplica la Matriz de Rotación (`Rot_1`) basada en sus grados de inclinación. Esto "gira" la perspectiva para calcular cómo se percibe esa posición desde el asiento del robot (**Local**).
3. **Transformación Inversa (Comprobación):** Finalmente, multiplica el resultado por la matriz inversa (`inv_Rot_1`) para hacer el paso contrario y comprobar que, matemáticamente, se regresa exactamente a las coordenadas iniciales del mapa global.
