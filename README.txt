Levitador Inteligente con Control PID y Análisis Físico
Descripción

Este proyecto implementa un sistema de levitación de una esfera utilizando un ventilador controlado por PWM, un sensor ultrasónico HC-SR04 y un microcontrolador (ESP32 o Arduino compatible con MicroPython).

El objetivo es mantener la bola suspendida a diferentes alturas dentro de un tubo mediante un sistema de control en lazo cerrado, integrando control PID, estrategias de feedforward, filtrado de señal y análisis físico del sistema.

Características principales
Control PID con:
Anti-windup
Derivada filtrada
Limitación de salida
Medición de distancia con sensor ultrasónico
Conversión calibrada de sensor a posición real
Control del ventilador mediante PWM
Feedforward basado en la altura deseada
Registro de datos en archivo CSV
Análisis automático de desempeño:
Tiempo de subida
Tiempo de establecimiento
Overshoot
Estimación de fuerza del ventilador
Estimación física en tiempo real:
Velocidad
Aceleración
Fuerza aplicada
Componentes utilizados
ESP32 o Arduino con MicroPython
Sensor ultrasónico HC-SR04
Ventilador DC (12V recomendado)
Fuente de alimentación
Tubo vertical
Bola liviana (icopor)
Protoboard y cables
Funcionamiento

El sistema realiza los siguientes pasos:

Mide la distancia de la bola con el sensor ultrasónico
Convierte la lectura a posición real en centímetros
Calcula el error respecto al setpoint
Aplica un controlador PID
Ajusta la velocidad del ventilador mediante PWM
Estima variables físicas como velocidad, aceleración y fuerza
Registra datos para análisis posterior
Control implementado
PID mejorado
Proporcional: responde al error actual
Integral: elimina el error estacionario
Derivativo: anticipa cambios
Incluye anti-windup y filtrado de derivada
Feedforward

Se utiliza un valor base de PWM según la altura deseada para mejorar la estabilidad y reducir el esfuerzo del controlador PID.

Salida de datos

El sistema genera un archivo llamado:

datos_levitacion.csv

Con las siguientes columnas:

tiempo_ms
posicion_cm
setpoint_cm
pwm
error_cm
derivada
Métricas de desempeño

Al finalizar la ejecución se muestran:

Tiempo de subida (10% a 90%)
Tiempo de establecimiento
Overshoot
Aceleración estimada
Fuerza del ventilador
Análisis de estabilidad
Uso
Cargar el código en el microcontrolador
Ejecutar el programa
Ingresar los límites de posición
Ingresar los setpoints (por ejemplo: 10, 20, 30)
Observar el comportamiento en consola
Detener con Ctrl + C para generar el reporte y guardar los datos
Consideraciones
El ventilador debe estar alineado con el tubo
El sensor debe ubicarse en la parte superior
La calibración sensor a posición es fundamental
No exceder el voltaje del ventilador
Posibles mejoras
Implementar control difuso combinado con PID
Crear una interfaz gráfica de monitoreo
Aplicar control adaptativo
Usar sensores más precisos
Optimizar automáticamente los parámetros PID
Autores

Mariana Moreno Duque
Cristian Grajales
Andrés Aguirre Restrepo
Diego Galindo Ortega

Contexto académico

Proyecto desarrollado para la asignatura de Inteligencia Artificial
Politécnico Jaime Isaza Cadavid – 2026
