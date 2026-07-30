---
title: 'Seguridad de las contraseñas y el usuario'
subtitle: 'Como entender las contraseñas'
description: 'Contraseñas fuertes, débiles, hashes e ingenio de usuarios'
pubDate: '2026-07-30'
heroImage: '../../../assets/blog/default-covers/ai-02.webp'
aiModel: 'anglefeint-core'
aiMode: 'narrative'
aiState: 'stable'
aiLatencyMs: 118
aiConfidence: 0.99
wordCount: 362
tokenCount: 860
---

Las contraseñas en la actualidad son muy importantes por eso veamos un poco más a detalle como evitar contraseñas inseguras. Pero antes veamos como se almacenan las contraseñas.

Las contraseñas no se almacenan en texto claro porque si un intruso logra robar las contraseñas puede usarla instantáneamente, no parece muy grave eso, puede ser la contraseña de una cuenta inofensiva o secundaria, tanto daño no puede hacer. Error! muchos usuarios reusan su contraseña en varias cosas porque es más fácil para su día a día que recordar varias contraseñas distintas.
Para evitar tener las contraseñas en texto claro por lo general las contraseñas se guardan como hashes, básicamente a la contraseña original se pasa por un proceso irreversible en el cual queda su “huella” conocida como hash. Esto permite que si un tercero tiene tu "contraseña" almacenada este no pueda tenerla en texto claro para usarla.

“Crackeado” de hashes. Bueno como el proceso de hasheado es irreversible no significa que el hash sea inútil se puede usar igualmente para obtener la contraseña original pero requiere mucho más esfuerzo. Básicamente se utiliza fuerza bruta que sería probar contraseñas una por una hasta que encuentre la contraseña correcta.

Velocidad del crackeado en local:
Esto depende de varios factores por lo que no se puede calcular de manera exacta lo que puede tardar el proceso. 
Empecemos con el mismo hash. El tipo de hash afecta mucho a la velocidad porque hay hashes que necesitan más poder de cómputo que otros para poder ser calculado. No es lo mismo crackear un hash md5 que SHA-256 ya que el segundo va a tardar mucho más en ser crackeado por lo tanto decimos que es más fuerte. 
Vamos a otro punto, la complejidad de la contraseña. Una contraseña de 8 caracteres puede parecer muy compleja de romper ante cualquier situación pero eso esta muy lejos de la realidad porque hay factores que reducen bastante el problema, lo cual es la políticas de la contraseña. Si una contraseña esta limitada a solo a números para romper una contraseña de 8 caracteres por fuerza bruta pura el máximo de posibilidades es 10⁸ = 100.000.000 un numero bastante bajo de posibilidades. Ahora planteemos lo mismo limitando solo a letras en minúsculas (ignoremos la ñ) son 26 a la 8 que equivale a 2,088 x 10 a la 11. Si lo comparamos el nuevo resultado con el anterior vemos que es más de 2000 veces más grande. Ahora veamos solo de letras mayúsculas y minúsculas 56 a la 8 = 9,671 x 10 a la 13, al aumentar tanto la cantidad de posibilidades romperlo se dificulta. No lo parece pero esto cambia todo pudiendo reducir horas, días, meses para crackear el hash conociendo de antemano las políticas de contraseñas. Usar contraseñas largas siempre va a tomar mas tiempo.
Por ultimo veamos el factor más importante del atacante la potencia de computación que tiene el mismo. Esto depende de la potencia de una gráfica porque se aprovecha mejor, a más potente la gráfica más rápida es la velocidad del crackeo pero no se limita a solo una gráfica.

Un hash y contraseña fuerte va a retrasar mucho el “crackeo” de una contraseña incluso puede que el atacante desista. No es lo mismo estar una semana o mes para romper una contraseña que 5 minutos, por eso el conocimiento sobre las mismas es muy importante.

Si bien el conocimiento anterior nos ayuda a mejorar la seguridad no sirve de nada si el usuario hace el menor esfuerzo por protegerse. Hay medidas poco efectivas para evitar estas situaciones como los requisitos y complejidad de contraseña pero no es que solucionen los problemas solo reducen el riesgo de una contraseña demasiado fácil. Veamos unos ejemplos de restricciones y el ingenio de un usuario para cumplir requisitos impuestos en una empresa ficticia de nombre “Inlane”

Contraseña mínimo de 9 caracteres:
"123456789"

Mínimo 9 caracteres con letras y números:
"inlane123"

Mínimo 9 caracteres con al menos una mayúscula,  una minúscula y números:
"Inlane123"

Mínimo 9 caracteres con al menos una mayúscula,  una minúscula, números y un símbolo especial:
"Inlane123!"

Como verán en los ejemplos anteriores todos cumplen los requisitos pero no son contraseñas muy seguras porque es el nombre de la empresa y un patrón muy simple de encontrar, el usuario siempre intentara recordar algo fácil. 
Pongamos otros ejemplos, supongamos que una vez al año tienen que cambiar la contraseña obligatoriamente y los requisitos son 10 caracteres de longitud entre números y letras

En 2024:
"inlane2024"

En 2025:
"inlane2025"

En 2026:
"inlane2026"

Se puede apreciar claramente que la contraseña no es segura pero cumple con los requisitos. Por lo tanto las políticas de contraseñas pueden ser efectivas pero no necesariamente te pueden dar buenos resultados porque el usuario se las puede ingeniar para reciclar su contraseña. Aunque la contraseña sea muy sencilla siempre y cuando sea lo suficientemente larga puede ser más segura que una más compleja

Contraseña larga:
peperitocomeguizoconmigo

Contraseña más compleja:
"Inlane2026!"

Se puede apreciar que la contraseña larga es más segura porque no tiene relación con la empresa, son una secuencia de palabras que la hacen fácil de recordar y le da una buena longitud. La contraseña más compleja posiblemente pueda ser encontrada con un esfuerzo menor porque es el nombre de la empresa, un año y un símbolo especial (Esto no es algo muy fuera de lo común a probar)

Conclusión:
Los usuarios pueden ser muy creativos a la hora de completar los requisitos de una contraseña y que no sea segura. Las políticas de contraseñas ayudan a evitar contraseñas débiles pero no lo solucionan. 
Los gestores de contraseñas y otras herramientas pueden ser una buena solución para evitar contraseñas débiles. Nota: si la contraseña de un gestor de contraseñas en local como keepass es muy débil se puede crackear y obtener las contraseñas guardadas y perder las contraseñas puede causar situaciones como esta:
https://youtu.be/5HdnrLtfbrI?si=ESMiBKs5ij9SY2ll&t=137
