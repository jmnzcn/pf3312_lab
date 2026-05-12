# Proyecto 1 — Agentes Virtuales (PF-3312)

Primer entregable del laboratorio de PF-3312, Agentes Virtuales Inteligentes
(Posgrado en Computación e Informática, UCR. I Ciclo, 2026).

El objetivo de esta entrega es seleccionar, justificar y dejar configurados
en Unity tres modelos 3D que servirán como base para construir agentes
virtuales en las entregas siguientes. Los personajes se escogieron buscando
registros visuales claramente distintos —Max como agente realista de
bienestar físico, Winston como personaje caricaturesco de entretenimiento
y Liam como tutor adolescente en estilo cartoon— porque cada uno tiene una
procedencia, una topología y un set de blend shapes diferente. Esto obliga
a validar el mismo flujo de expresión facial, lip-sync y animación corporal
sobre tres pipelines técnicos distintos, que es justamente lo que se busca
demostrar en esta etapa.

El proyecto está implementado en Unity 6000.3.11f1 con Universal Render
Pipeline (URP).

## Cómo abrir el proyecto

Abrir la carpeta `NeyFred_Jimenez/` desde Unity Hub usando la versión
6000.3.11f1. La primera importación tarda varios minutos porque se generan
los caches de shaders y blend shapes; una vez termine, basta con abrir
cualquiera de las escenas dentro de `Assets/Scenes/` (`Max.unity`,
`Winston.unity` o `Liam.unity`) y darle Play.

Cada escena expone un Canvas con el mismo esquema de control: expresiones
faciales del lado izquierdo, acciones físicas del lado derecho, un botón
central de Hablar que reproduce el audio TTS sincronizado con la animación
facial, y dos cámaras (Cam 1 de cuerpo completo, Cam 2 de rostro en primer
plano).

## Personajes

### Max

Acompañante de bienestar físico, pensado para contextos de gimnasio o de
asistente de entrenamiento. Es un humanoide masculino atlético, calvo, con
short deportivo, ambientado en un gimnasio industrial. El modelo proviene
del asset Max iClone Character de Reallusion (Unity Asset Store, versión
1.03, licencia EULA estándar, gratuito).

Acciones físicas disponibles: Idle, PushUps, Saludar, Burpee y
QuedarseQuieto. Las expresiones faciales son Alegría, Tristeza, Duda y
Neutral. El rigging es humanoid sobre la nomenclatura de Character Creator,
lo que permite aplicar animaciones de Mixamo por retargeting sin pasos
adicionales.

Código: `Assets/Scripts/Max.cs`.

### Winston

Personaje caricaturesco de proporciones exageradas (piernas largas, torso
compacto, rasgos faciales angulosos, mohawk). Se eligió como agente de
entretenimiento y, sobre todo, como contraste estético frente a Max para
poder comparar dos estilos del mismo pipeline. El modelo es el asset
Winston iClone Character de Reallusion (Unity Asset Store, versión 1.03,
licencia EULA estándar, gratuito).

Acciones físicas disponibles: Idle, Pelear, Bailar y DeAcuerdo. Comparte
con Max las cuatro expresiones faciales y la misma estructura de blend
shapes.

Código: `Assets/Scripts/Winston.cs`.

### Liam

Tutor adolescente en estética cartoon stylized, pensado para escenarios
educativos. A diferencia de los dos anteriores, el modelo no viene del
pipeline de Reallusion sino del asset 1 Toon Teen de JBGarraza (Unity Asset
Store, versión 1.3, licencia EULA estándar, gratuito). El esqueleto sigue
siendo humanoid, así que las animaciones de Mixamo siguen siendo
compatibles, pero los blend shapes están organizados con otra convención;
parte del valor de incluirlo es precisamente comprobar que el mismo sistema
de control funciona sobre un pipeline distinto.

Acciones físicas disponibles: Idle, Confianza, Guitarra, Jugar y
QuedarseQuieto.

Código: `Assets/Scripts/Liam.cs`.

## Estructura del proyecto

Solo lo relevante para revisar la entrega:

- `Assets/Scripts/`: la lógica de cada agente (`Max.cs`, `Winston.cs`,
  `Liam.cs`).
- `Assets/Scenes/`: una escena por agente.
- `Assets/Modelos/`: FBX, materiales, texturas, prefab y animaciones de
  cada personaje, separados por subcarpeta.
- `Assets/Prefabs/`: el Canvas compartido por las tres escenas.
- `Assets/Sonidos/`: clips de voz TTS por personaje.
- `Assets/Imagenes/`: fondos usados como escenarios (gimnasio, granja,
  fondo neutro).

Las animaciones físicas se obtuvieron de Mixamo y se aplicaron por
retargeting sobre el avatar humanoid de cada modelo.

## Videos de demostración

- Max: https://youtu.be/1mlcplqlNbc
- Winston: https://youtu.be/Gz3U2PqKKbk
- Liam: https://youtu.be/DR3c7ND_fFs

## Documento de la entrega

El documento formal con la selección, la justificación estética, el marco
teórico, los datos técnicos detallados (rigging, blend shapes, conteos
poligonales, lip-sync) y las referencias bibliográficas se encuentra en
`Docs/Proyecto1_Lab_NeyFredJimenez_B03230.pdf`. Este README solo busca dar
contexto operativo al proyecto en Unity.
