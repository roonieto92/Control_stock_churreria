# Control_stock_churreria
Módulo de control de stock de materias primas para churrería "Tamara"

Desarrollado para la cátedra "Organización empresarial" Trabajo Práctico Integrador. TUPaD cuatrimestre Agosto 2026.
Integrante: Nieto, Rocio.

El módulo de control de stock esta pensado para registrar movimientos de materias primas en las cocinas de dicho local, y generar un pedido automático a sus proveedores.

Mecanismos de Control y Uso Crítico de Herramientas: 
En la entrega 2 del TPI se establecieron los siguientes, objetivo y metas
“Objetivo: Realizar un módulo de control de stock para churrería “Tamara” que permita al usuario ingresar que cantidad de insumos se usa, y, ante la baja de cierta cantidad establecida de los productos genere un pedido automático para enviar al proveedor correspondiente.
Metas: 
•	Registrar movimientos de los insumos en 5 segundos.
•	Mantener control de los movimientos de 8 insumos distintos sin enlentecer el programa.
•	Registrar en 15 segundos el pedido ante la baja de stock.”
Se presentaran 4 items relacionados con ellos, y cada uno tendría una medida de indicador de control y una medida de estándar de desempeño.
1. Tiempo de Procesamiento de insumos:
Indicador de Control: El tiempo de respuesta del sistema desde que el personal de cocina confirma el uso de un insumo hasta que se actualiza el stock_actual.
Estándar de Desempeño: El registro y descuento debe completarse en un tiempo máximo de 5 segundos.
.
2. Tiempo de generación de orden de compra:
Indicador de Control: La velocidad con la que el software evalúa la condición de stock (stock_actual <= stock_minimo) y realiza el borrador.
Estándar de Desempeño: El borrador de pedido debe generarse en un máximo de 15 segundos tras registrarse la baja.
3. Precisión del Cálculo de movimientos:
Indicador de Control: Congruencia entre los movimientos registrados (entradas y salidas) y el registro en la base de datos.
Estándar de Desempeño: Sin margen de error en el cálculo del inventario (sumas por reingreso y restas por consumo).
4. Disponibilidad del Sistema:
Indicador de Control: La operatividad continua del módulo de software durante los horarios de producción de la churrería.
Estándar de Desempeño: Disponibilidad de 99%, evitando interrupciones o caídas del sistema durante las jornadas de elaboración.

Declaración de uso de IA
Se utilizó Gemini Notebook, con las consignas, para explicación de conceptos aplicados al TP (BPMN, compuertas, KPIs) , propuesta de un flujo base para el proceso de inventario; redacción inicial de las Historias de Usuario en base a ideas sueltas, verificación de los indicadores, y guía para usar GitHub Projects. A continuación se detallan los prompts clave utilizados, y las propuestas que tomaron.


Prompt (textual)	Por qué lo formulé así 	Resultado
 "…es un sistema de control de inventario para una churrería/panadería… ¿se refiere a cómo se usaría o en qué sector?" 	No tenía claro qué pedía la consigna 1 y cite el caso de mis entregas	Flujo base con pools, compuerta de stock mínimo y aprobación humana.
“¿Podría esperar el evento (que llegue la mercadería) y ahí continuarlo?”	Considerar si una vez enviada la solicitud se considera un proceso aparte o no	Evento intermedio de espera para cerrar el ciclo con la recepción de mercadería
"Es un poco similar a la historia de usuario 2"	Noté que las historias de usuario 2 y 3 que sugería se superponían.	Reescribió ambas separando detección y autorización
"¿De dónde sale eso, de qué apunte? No lo vi nunca" 	No podía defender fórmulas que no vi en la cursada	Reformuló los indicadores en lenguaje descriptivo

Mis correcciones en base a la propuesta de la IA
Propuesta de la IA	Mi corrección	Motivo
Historia 2 como panel de alertas
	Recibir un borrador de pedido	En mi diagrama el software genera un borrador que compras revisa, y mi Entrega 2 planteaba que el sistema genere el pedido ante la baja de stock
Historia 3 con rol "Administrador / Personal de Depósito"	Propietario, con redacción propia	Organigrama de la Entrega 3
Indicadores con fórmulas y meta de 24 h	Descartados	No figuran en los apuntes de la cursada
Aprobación humana antes del envío	La mantuve tras cuestionarla	Quería que una persona controle el gasto antes de que el sistema envíe el pedido

Reflexión: La IA fue útil para ordenar ideas y utilizar algunas de sus propuestas, pero en varios puntos no coincidía con lo que ya había desarrollado en mis entregas anteriores, tuve que contrastar cada propuesta con mi organigrama diccionario de datos y metas. Propuso fórmulas y estándares numéricos que no estaban en los apuntes ni podía justificar, y redactó historias de usuario, en base a mis ideas, que se superponían; ambas cosas las detecté y pude corregir. Asumo la responsabilidad del contenido entregado.
