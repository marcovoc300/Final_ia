# 📊 DataStory AI - Pipeline de Análisis Ejecutivo (POC)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/marcovoc300/Final_ia/blob/main/IA_entrega_final.ipynb)
#📝 Resumen
#DataStory AI es una Prueba de Concepto (POC) diseñada para resolver la saturación cognitiva de datos en PyMEs de e-commerce. A través de un pipeline trimodal que combina inferencia de lenguaje con la API de Groq, generación de visualizaciones de datos en Python (Matplotlib/Pandas) y la integración de assets visuales de apoyo mediante modelos de generación de imagen (Ideogram/Midjourney), el sistema transforma métricas transaccionales complejas en diagnósticos ejecutivos narrativos estructurados e informes visuales listos para la toma de decisiones.
#📌 Introducción
#Presentación del Problema a Abordar
#En el sector e-commerce, las PyMEs suelen recopilar grandes volúmenes de datos sobre ventas, tráfico y comportamiento de usuarios. Sin embargo, carecen de equipos dedicados de Business Intelligence para interpretar estos datos de manera rápida. Los tableros tradicionales muestran gráficos aislados pero no explican la causa raíz de las desviaciones de negocio ni proponen acciones concretas, lo que genera parálisis por análisis o decisiones tardías.
#Desarrollo de la Propuesta de Solución
#La solución propone entretejer lógica algorítmica y modelos de Inteligencia Artificial para automatizar la interpretación analítica. Se desarrolló un script en Python que toma métricas críticas de negocio (ventas, tráfico, conversión, abandono de carrito y quejas logísticas) y las procesa mediante la API de Groq (Llama 3) bajo técnicas avanzadas de Fast Prompting. El modelo actúa como un consultor senior que diagnostica el conflicto, identifica la causa raíz y redacta resoluciones tácticas inmediatas, complementadas con visualizaciones cuantitativas generadas por código y elementos gráficos conceptuales.
#Justificación de la Viabilidad del Proyecto
#El proyecto es altamente viable desde el punto de vista técnico y económico:
#Recursos de Cómputo: Se ejecuta de forma gratuita sobre infraestructura de Google Colab en la nube.
#Modelos de Inferencia (Texto-Texto): La API de Groq ofrece acceso de ultrabaja latencia y sin costo en sus capas de prueba para modelos de código abierto como llama-3.3-70b-versatile.
#Seguridad: Utiliza la gestión de variables de entorno de Colab Secrets (google.colab.userdata), evitando la exposición de claves en repositorios públicos.
#Tiempo e Implementación: La arquitectura modular en Python permite la ejecución completa del pipeline en menos de 5 segundos.
#🎯 Objetivos
#Objetivo General: Desarrollar una POC funcional mediante un cuaderno ejecutable en Google Colab que interprete métricas de e-commerce y genere un informe ejecutivo claro usando modelos de IA y código.
#Objetivos Específicos:
#Implementar técnicas de Fast Prompting (Role Prompting, Chain-of-Thought, restricciones negativas) sobre la API de Groq.
#Diseñar un mecanismo de resiliencia de software (fallback system) que detecte y pruebe iterativamente modelos de chat disponibles.
#Integrar la generación de gráficos cuantitativos en Matplotlib con prompts para herramientas de generación de imágenes de apoyo ejecutivo.
#🧠 Metodología
#El proyecto se dividió en cuatro fases de desarrollo:
#Fase 1 - Configuración de Entorno y Seguridad: Ingesta de dependencias y desacople seguro de credenciales GROQ_API_KEY mediante google.colab.userdata.
#Fase 2 - Ingeniería de Prompts (Texto-Texto): Diseño e iteración del SYSTEM_PROMPT aplicando estructuración jerárquica obligatoria (Titular, Conflicto, Clímax y Resolución).
#Fase 3 - Inferencia y Fallback: Conexión dinámica a la API de Groq, filtrado de catálogo activo y ejecución secuencial en cascada para prevenir errores de cuota o servicio.
#Fase 4 - Generación de Assets de Apoyo (Texto-Imagen): Elaboración y prueba de un prompt optimizado para herramientas de generación de imágenes generativas (como Ideogram o Nightcafe) para crear un gráfico conceptual publicitario que ilustre el informe.
#🛠️ Herramientas y Tecnologías (Fast Prompting)
#Tecnologías Utilizadas
#Lenguaje: Python 3.x en Google Colab.
#Librerías: groq, pandas, matplotlib, google.colab.userdata.
#API de IA: Groq SDK (Llama 3.3 70B Versatile / Llama 3.1 8B Instant).
#Generación de Imagen: Ideogram / Nightcafe (Herramienta externa gratuita).
#Justificación de Técnicas de Fast Prompting Aplicadas
#Role Prompting: Se asignó al modelo el rol de "Consultor Senior en Data Storytelling para PyMEs" para forzar un lenguaje ejecutivo, profesional y orientado a resultados.
#Negative Prompting (Restricciones): Se prohibió explícitamente el uso de jerga estadística compleja y se exigió basarse únicamente en los datos provistos para evitar alucinaciones.
#Structured Output (Chain-of-Thought implícito): Se obligó al modelo a dividir la respuesta en 4 bloques lógicos (Titular de Impacto -> Conflicto -> Clímax/Causa Raíz -> Resolución Táctica).
#Implementación
#1. Módulo Texto-Texto (Código Python / API Groq)
#El código completo y funcional se encuentra publicado y ejecutable en el notebook IA_entrega_final.ipynb dentro de este repositorio.
#2. Módulo Texto-Imagen (Generación de Asset de Apoyo)
#Dado que las APIs de generación de imágenes (como DALL-E) son de pago, se utilizó una herramienta gratuita externa (Ideogram/Nightcafe) aplicando la siguiente especificación de prompt:
#Prompt de Imagen Utilizado:
#"A professional minimalist executive dashboard presentation background, 3D isometric style, showing a declining conversion graph turning into a rising solution arrow, corporate blue and orange color palette, clean design, studio lighting, high resolution, 8k --no photorealistic people, blur"

#Salida de Imagen:
#(La imagen del resultado generado fue integrada dentro de las celdas Markdown del cuaderno ejecutable en Google Colab).
#📈 Resultados
#La ejecución del pipeline sobre el escenario crítico planteado (Aumento de tráfico del +20%, caída de ventas del -15%, baja de conversión al 1.2% y 65% de quejas por costos logísticos) produjo los siguientes resultados:
#Diagnóstico Narrativo Consolidado: El LLM aisló con éxito la causa raíz: el aumento del costo de envío del nuevo operador logístico neutralizó la inversión en pauta publicitaria, causando un abandono del 40% en el checkout.
#Recomendaciones Tácticas: La IA generó 3 medidas inmediatas priorizadas (renegociación con operador, subsidio temporal en flete y optimización del checkout).
#Resiliencia Técnica: El script ejecutó el catálogo dinámico de modelos sin interrupciones ni fallos de autenticación.
#🔚 Conclusiones
#Cumplimiento de Objetivos: Se cumplió el 100% de los objetivos propuestos, logrando una Prueba de Concepto funcional que integra código, inferencia de texto y generación de imágenes.
#Relevancia del Fast Prompting: Se demostró que un prompt fuertemente estructurado y restringido elimina las alucinaciones numéricas en modelos LLM, volviéndolos aptos para consultoría de negocios.
#Separación de Responsabilidades: El enfoque trimodal (código para cómputo, LLM para narrativa e imagen generativa para representación) es la arquitectura ideal para aplicaciones reales de Ciencia de Datos en PyMEs.
#📚 Referencias
#Documentación de la API de Groq: https://console.groq.com/docs
#Llama 3 Architecture and Prompting Guide (Meta AI): https://www.llama.com/
#Google Colab Userdata API: https://colab.research.google.com/
