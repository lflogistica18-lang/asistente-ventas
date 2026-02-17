# Asistente de Ventas - Control de Plagas (Skill)

Skill de Claude Code para cotizar servicios de control de plagas. Los vendedores consultan y el asistente diagnostica, calcula insumos, detecta zona y entrega cotizacion final con mensaje copy-paste para el cliente.

## Stack

- Skill de Claude Code (sin codigo, todo en Markdown)
- Interfaz web en `index.html` (HTML standalone, sin dependencias)
- Precios en pesos argentinos (ARS)

## Archivos y cuando se consultan

| Archivo | Proposito | Paso del flujo |
|---|---|---|
| SKILL.md | Cerebro: flujo de 7 pasos, formato de salida, reglas | Siempre |
| REGLAS-GLOBALES.md | Reglas transversales: localidad, m2, combos, recargos, alertas | Paso 2 (siempre) |
| FICHA-PLAGAS-V02.md | Fichas por plaga: preguntas, insumos, alertas, equipo | Paso 4 (segun plaga) |
| INSUMOS.md | Precios unitarios y formulas de calculo | Paso 5 |
| PRECIOS-ZONAS.md | Localidades, clasificaciones, precios base | Paso 6 |
| RESPUESTA-CLIENTE.md | Template copy-paste para WhatsApp + consultas frecuentes | Paso 7 |
| ENTRENAMIENTO.md | Explicaciones del "por que" de cada regla | Solo modo entrenamiento |
| CASOS-PENDIENTES.md | Log de situaciones no cubiertas | Automatico |

## Flujo resumido

```
Mensaje vendedor → Parsear datos → Validar caso → Diagnostico plaga
→ Calcular insumos → Detectar zona/precio → Doble salida:
  1. Mensaje copy-paste para el cliente (WhatsApp)
  2. Cotizacion interna del vendedor
```

## Reglas clave

- Doble salida siempre: mensaje cliente (sin tecnicismos) + cotizacion interna (con alertas tecnicas)
- Domicilios interior siempre cotizan como "hasta 1000m2"
- Combo 2 plagas: servicio mayor completo + segundo al 20%
- Combo 3+: mostrar individuales y pares, vendedor decide
- >5000m2 o chinches en hoteles → derivar a Lucas
- Recargos horarios: antes 17hs 0%, 17-20 +20%, 20-22 +35%, 22-01 +50%
- Factura A o transferencia → total + IVA 21%
- No hacemos: aves, madera, roedores domiciliarios, domingos

## Convenciones de edicion

- Cada dato vive en un solo archivo (fuente unica de verdad)
- Plaga nueva → agregar ficha en FICHA-PLAGAS-V02.md + formula en INSUMOS.md
- Localidad nueva → agregar en PRECIOS-ZONAS.md
- Precios → modificar en el archivo correspondiente (PRECIOS-ZONAS o INSUMOS)
- Casos no cubiertos se registran automaticamente en CASOS-PENDIENTES.md
