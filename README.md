# Proyecto 1 — Agentes Virtuales (PF-3312)

Primer entregable del laboratorio del curso PF-3312, Agentes Virtuales
Inteligentes, del Posgrado en Computación e Informática de la UCR
(I Ciclo, 2026).

En esta entrega se preparan en Unity tres modelos 3D para usarlos como
agentes virtuales en las próximas entregas. Cada uno representa un estilo
visual distinto: Max es realista (atlético), Winston es caricaturesco y
Liam es cartoon. La idea de combinar los tres es probar el mismo flujo de
expresión facial, lip-sync y animación corporal sobre pipelines técnicos
diferentes.

Hecho en Unity 6000.3.11f1 con URP.

## Cómo abrir el proyecto

Abrir la carpeta `NeyFred_Jimenez/` desde Unity Hub con la versión
6000.3.11f1. La primera importación tarda varios minutos porque se
generan los caches de shaders y blend shapes. Una vez termine se puede
abrir cualquiera de las escenas en `Assets/Scenes/` (`Max.unity`,
`Winston.unity` o `Liam.unity`) y darle Play.

Cada escena tiene un Canvas con el mismo esquema: expresiones faciales a
la izquierda, acciones físicas a la derecha, un botón Hablar al centro y
dos cámaras (Cam 1 de cuerpo completo y Cam 2 de rostro).

## Personajes

### Max

Acompañante de bienestar físico. Humanoide masculino atlético, calvo,
con short deportivo, ambientado en un gimnasio industrial. El modelo es
Max iClone Character de Reallusion (Unity Asset Store, v1.03, licencia
EULA estándar, gratuito).

Acciones físicas: Idle, PushUps, Saludar, Burpee, QuedarseQuieto.
Expresiones: Alegría, Tristeza, Duda, Neutral. El rigging es humanoid
con la nomenclatura de Character Creator, así que las animaciones de
Mixamo se aplican por retargeting sin pasos adicionales.

Código: `Assets/Scripts/Max.cs`.

### Winston

Personaje caricaturesco de proporciones exageradas: piernas largas,
torso compacto, rasgos faciales angulosos, mohawk. Funciona como agente
de entretenimiento y como contraste estético frente a Max, para comparar
dos estilos del mismo pipeline. Asset Winston iClone Character de
Reallusion (Unity Asset Store, v1.03, licencia EULA estándar, gratuito).

Acciones físicas: Idle, Pelear, Bailar, DeAcuerdo. Comparte con Max las
mismas expresiones faciales y la misma estructura de blend shapes.

Código: `Assets/Scripts/Winston.cs`.

### Liam

Tutor adolescente en cartoon stylized, pensado para escenarios
educativos. A diferencia de los otros dos, no viene del pipeline de
Reallusion sino del asset 1 Toon Teen de JBGarraza (Unity Asset Store,
v1.3, licencia EULA estándar, gratuito). El esqueleto sigue siendo
humanoid, así que las animaciones de Mixamo también funcionan, aunque
los blend shapes están organizados con otra convención.

Acciones físicas: Idle, Confianza, Guitarra, Jugar, QuedarseQuieto.

Código: `Assets/Scripts/Liam.cs`.

## Estructura del proyecto

Lo relevante para revisar la entrega:

- `Assets/Scripts/`: lógica de cada agente (`Max.cs`, `Winston.cs`,
  `Liam.cs`).
- `Assets/Scenes/`: una escena por agente.
- `Assets/Modelos/`: FBX, materiales, texturas, prefab y animaciones de
  cada personaje.
- `Assets/Prefabs/`: el Canvas compartido por las tres escenas.
- `Assets/Sonidos/`: clips de voz TTS por personaje.
- `Assets/Imagenes/`: fondos usados como escenarios.

Las animaciones físicas vienen de Mixamo y se aplicaron por retargeting
sobre el avatar humanoid de cada modelo.

## Videos

- Max: https://youtu.be/1mlcplqlNbc
- Winston: https://youtu.be/Gz3U2PqKKbk
- Liam: https://youtu.be/DR3c7ND_fFs

## Documento de la entrega

La justificación estética, el marco teórico, los datos técnicos
detallados (rigging, blend shapes, conteos poligonales, lip-sync) y las
referencias están en `Docs/Proyecto1_Lab_NeyFredJimenez_B03230.pdf`.
