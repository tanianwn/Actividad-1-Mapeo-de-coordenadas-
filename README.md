# Actividad 1 Mapeo de coordenadas

### 1. Sistema de Referencia Inercial (El Global o "El Mundo")
* **¿Qué es?:** Es el mapa fijo y absoluto. Es un punto de origen dibujado en el piso o en el mundo que **nunca se mueve**. 
* **En el código:** Son las coordenadas iniciales de la tabla de datos definida donde se incluyen los incisos de la activdiad (por ejemplo, `x = -5, y = 9`). Representan en qué punto exacto del mundo global está el robot.



### 2. Sistema de Referencia Local (El del propio Robot)
* **¿Qué es?:** Es la perspectiva "en primera persona" del robot. El marco está "pegado" a su chasis o a el mismo. En el robot, es siempre su centro u origen `0,0` y el "frente" suyo siempre es su eje X, sin importar hacia dónde esté apuntando dentro del sistema inercial o del mundo.
* **En el código:** Es el vector resultante que se guarda en la variable `xi_local_1`.

---

### 3. Mapeo (actividad)
Los pasos realizados en el codigo son los siguientes:
1. **Punto de partida:** se toma la posición del robot en el mundo fijo (**Inercial**).
2. **Transformación Directa:** se le aplica la Matriz de Rotación (`Rot_1`) basada en sus grados de inclinación. Esto hace girar la perspectiva para calcular cómo se percibe esa posición desde el robot (**Local**).
3. **Transformación Inversa (Comprobación):** Finalmente, se multiplica el resultado por la matriz inversa (`inv_Rot_1`) para hacer el paso contrario y comprobar que, matemáticamente, se regresa exactamente a las coordenadas iniciales del mapa global.

## Imágen del robot
<p align="center">
  <img src="https://github.com/user-attachments/assets/6be165b3-e465-4acb-9c78-efacfa8af3cd" width="600" alt="Robot Cartesiano 3GDL"/>
</p>

