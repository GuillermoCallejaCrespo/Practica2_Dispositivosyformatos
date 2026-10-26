# Práctica 2 – Pinball en Unreal Engine 5

## Descripción del proyecto

Desarrollo de una máquina de pinball jugable en Unreal Engine 5 utilizando Blueprints y Enhanced Input System.

El jugador comienza en primera persona y, al acercarse a la máquina, toma su control mediante Possess. El pinball incorpora flippers animados, una bola con simulación física, rebotadores, lanzador, reinicio de la bola y sistema de puntuación.

## 1. Controles

| Acción | Teclado | 
|---|---|
| Flipper izquierdo (`blipper_izqd`) | Flecha izquierda |
| Flipper derecho (`blipper_dcha`) | Flecha derecha |
| Lanzador (`lanzador`) | Flecha arriba |
| Reiniciar (`reiniciar`) | R |

Los controles de teclado están implementados mediante `IMC_pinball`.

## 2. Configuración física de la bola

| Parámetro | Valor |
|---|---|
| Escala de la esfera | 0.025 |
| Simulate Physics | Activado |
| Mass | 0.4 kg |
| Linear Damping | 0.01 |
| Angular Damping | 0.0 |
| Collision Presets | PhysicsActor |
| Simulation Generates Hit Events | Activado |
| Generate Overlap Events | Activado |
| CCD | Activado |
| Inertia Conditioning | Desactivado |
| Sleep Family | Custom |
| Custom Sleep Threshold Multiplier | 0 |

### Material físico: bolaphysicalmaterial

| Parámetro | Valor |
|---|---|
| Friction | 0.05 |
| Static Friction | 0.0 |
| Restitution | 0.75 |

## 3. Funcionalidades implementadas

- Cambio automático del control del personaje a la máquina mediante Possess.
- Cambio de contexto de entrada mediante Enhanced Input System.
- Movimiento de los dos flippers mediante Timelines de 0.1 segundos.
- Rotación del flipper izquierdo de 0° a −50° y del derecho de 0° a +50°.
- Lanzamiento de la bola mediante impulso físico al soltar la tecla correspondiente.
- Reinicio de la bola en el carril de salida mediante la tecla R.
- Rebotadores que aplican impulsos adicionales al detectar el impacto de la bola.
- Sistema de puntuación con un marcador Text Render.

## 4. Mejoras implementadas

**Sistema de puntuación ampliado:** además de los 50 puntos obtenidos al golpear un bouncer, se ha creado la función `Puntuar Elemento` para otorgar 25 puntos al golpear componentes con las etiquetas `diana` o `goma`.

**Reinicio manual de la bola:** permite devolver la bola al carril de salida sin tener que reiniciar la partida. El sistema desactiva temporalmente la simulación física, reposiciona la bola y vuelve a activarla.

**Corrección de la masa de la bola, de 0,5kg a 0,4kg para que los flippers lograran darla más velocidad.

No se han añadido todavía efectos audiovisuales personalizados adicionales.

## 5. Ejecución

1. Abrir el archivo `Practica2.uproject` con una versión compatible de Unreal Engine 5.
2. Ejecutar mediante Play In Editor.
3. Acercarse a la máquina de pinball para tomar su control.
4. Utilizar las flechas para mover los flippers y lanzar la bola.
5. Pulsar R para reiniciar la bola cuando sea necesario.

El proyecto utiliza la plantilla First Person e incluye los modelos y elementos del pinball proporcionados como base para la práctica.
