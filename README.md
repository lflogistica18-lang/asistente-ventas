# Asistente de Ventas - Control de Plagas (Skill)

## Qué es esto

Skill para asistente de ventas que cotiza servicios de control de plagas. Desde la consulta inicial hasta el precio final, sin pasos intermedios.

## Archivos

| Archivo | Función | ¿Cuándo se usa? |
|---|---|---|
| SKILL.md | Cerebro principal. Flujo de 7 pasos, formato de salida, reglas de operación | Siempre |
| REGLAS-GLOBALES.md | Reglas que aplican a toda plaga (localidad, m², alertas, restricciones) | Siempre |
| FICHAS-PLAGAS.md | Ficha compacta por cada plaga (preguntas, insumos, alertas, equipo) | Según plaga detectada |
| INSUMOS.md | Precios unitarios y fórmulas de cálculo de insumos | Cuando hay insumos |
| PRECIOS-ZONAS.md | Localidades, clasificaciones, precios base y fórmula de aumento | Para calcular precio final |
| ENTRENAMIENTO.md | Explicaciones del "por qué" de cada regla y pregunta | Solo en modo entrenamiento |

## Cómo funciona

```
Vendedor escribe consulta
  → Parsear datos mencionados
  → Validar caso (¿hacemos esto? ¿derivar?)
  → Diagnosticar según ficha de la plaga
  → Calcular insumos
  → Detectar zona y precio base
  → Entregar cotización final con total
```

## Cómo agregar una plaga nueva

1. Abrir FICHAS-PLAGAS.md
2. Copiar la plantilla vacía del inicio del archivo
3. Completar los campos (preguntar, insumos, alertas, equipo, post-servicio)
4. Si tiene insumos nuevos, agregar la fórmula en INSUMOS.md
5. Listo. Las reglas globales ya aplican automáticamente.

## Cómo agregar una localidad nueva

1. Abrir PRECIOS-ZONAS.md
2. Determinar la clasificación según distancia en km
3. Agregar el nombre bajo el partido correspondiente en la clasificación correcta
4. Listo. La fórmula de precio ya aplica automáticamente.

## Cómo cambiar precios

- **Precio base de un servicio** → modificar tabla en PRECIOS-ZONAS.md (sección "Tabla de precios base")
- **Porcentaje de aumento por zona** → modificar tabla en PRECIOS-ZONAS.md (sección "Aumento por clasificación")
- **Precio de un insumo** → modificar tabla en INSUMOS.md (sección "Tabla de precios unitarios")

Cada dato vive en un solo lugar. Un cambio, una edición.

## Plagas soportadas

Insectos Rastreros: Pulgas, Garrapatas, Chinches, Cucarachas, Hormigas, Arañas, Gorgojos
Insectos Voladores: Mosquitos, Moscas, Polillas
Roedores: Ratas, Ratones (solo empresas)
Otros: Desinfección

## No hacemos

- Control de aves
- Plagas de la madera (termitas, bicho taladro)
- Roedores en domicilios particulares
- Servicios los domingos

## Versión

1.0 - Febrero 2026
