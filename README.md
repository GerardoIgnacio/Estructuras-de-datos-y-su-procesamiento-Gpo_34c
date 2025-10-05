# Evidencia Escolar - Procesamiento de Datos con Python

## Descripción
Programa en Python que utiliza NumPy y pandas para procesar datos de calificaciones estudiantiles.

## Características
- Generación de datos con arreglos NumPy
- Análisis estadístico con operaciones NumPy
- Exportación a formato CSV
- Cálculo de promedios por materia

## Resultados
- Promedio general: [promedio_calculado]
- Materia con mejor promedio: [materia_mejor_promedio]
- Archivo generado: `Ev2.1.csv`# EVIDENCIA ESCOLAR - Procesamiento de Datos con NumPy y pandas
print("=== EVIDENCIA 2.1 - PROCESAMIENTO DE DATOS ===")

import numpy as np
import pandas as pd

np.random.seed(42)

# Arreglos NumPy para datos estudiantiles
estudiantes = np.array(['Ana', 'Luis', 'Maria', 'Carlos', 'Elena'])
materias = np.array(['Matemáticas', 'Ciencias', 'Historia', 'Español', 'Programación'])

# Generar datos con NumPy
calificaciones = np.random.randint(60, 101, 20)
comentarios = np.array([
    'Excelente trabajo', 'Buen desempeño', 'Puede mejorar', 'Sobresaliente',
    'Muy responsable', 'Creativo', 'Esfuerzo notable', 'Participación activa',
    'Comprensión buena', 'Trabajo en equipo', 'Análisis crítico', 'Investigación completa',
    'Presentación clara', 'Dominio del tema', 'Atención en clase', 'Mejora continua',
    'Responsable', 'Puntual en entregas', 'Buen seguimiento', 'Resultados destacados'
])

# Crear DataFrame
datos = {
    'Estudiante': np.tile(estudiantes, 4),
    'Materia': np.tile(materias, 4),
    'Calificación': calificaciones,
    'Comentario': comentarios
}

df = pd.DataFrame(datos)

# Análisis con NumPy
promedio_general = np.mean(calificaciones)
mejor_materia = df.groupby('Materia')['Calificación'].mean().idxmax()
mejor_promedio = df.groupby('Materia')['Calificación'].mean().max()

# Mostrar resultados
print("\n📊 DATASET CREADO:")
print(df.head(10))
[2.1csv (1).txt](https://github.com/user-attachments/files/22704998/2.1csv.1.txt)
Estudiante,Materia,Calificación,Comentario
Ana,Matemáticas,98,Excelente trabajo
Luis,Ciencias,88,Buen desempeño
Maria,Historia,74,Puede mejorar
Carlos,Español,67,Sobresaliente
Elena,Programación,80,Muy responsable
Ana,Matemáticas,98,Creativo
Luis,Ciencias,78,Esfuerzo notable
Maria,Historia,82,Participación activa
Carlos,Español,70,Comprensión buena
Elena,Programación,70,Trabajo en equipo
Ana,Matemáticas,83,Análisis crítico
Luis,Ciencias,95,Investigación completa
Maria,Historia,99,Presentación clara
Carlos,Español,83,Dominio del tema
Elena,Programación,62,Atención en clase
Ana,Matemáticas,81,Mejora continua
Luis,Ciencias,61,Responsable
Maria,Historia,83,Puntual en entregas
Carlos,Español,89,Buen seguimiento
Elena,Programación,97,Resultados destacados

print(f"\n📈 ANÁLISIS ESTADÍSTICO:")
print(f"Promedio general: {promedio_general:.1f}")
print(f"Materia con mejor promedio: {mejor_materia} ({mejor_promedio:.1f})")
print(f"Calificación máxima: {np.max(calificaciones)}")
print(f"Calificación mínima: {np.min(calificaciones)}")
print(f"Total de registros: {len(df)}")

# Guardar archivo CSV
archivo_csv = 'Ev2.1.csv'
df.to_csv(archivo_csv, index=False, encoding='utf-8')
print(f"\n✅ ARCHIVO GENERADO: '{archivo_csv}'")
print("🎉 ¡EVIDENCIA 2.1 COMPLETADA!")

## Tecnologías
- Python 3
- NumPy
- pandas

## Estructura del Dataset
- Estudiante: Nombre del estudiante
- Materia: Asignatura cursada
- Calificación: Puntuación obtenida (60-100)
- Comentario: Evaluación cualitativa del desempeño
