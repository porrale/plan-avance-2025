index_md = """# 📘 Índice de Unidades - Curso de Diseño Digital Avanzado

Bienvenido al repositorio del curso. Aquí encontrarás los resúmenes y materiales organizados por unidad.

---

## 🗂️ Unidades

- [Resumen - Unidad 0 - Introducción y Presentación del Curso](resumen_0.md)
- [presentación - Unidad 0 ()]
- [Unidad 1 - Introducción a Verilog](unidad_1.md)
- [Unidad 2 - Implementación de Sistemas Digitales](unidad_2.md)
- [Unidad 3 - Mapeo de Arquitecturas Dedicadas](unidad_3.md)
- [Unidad 4 - Bloques Básicos en FPGA/ASIC](unidad_4.md)
- [Unidad 5 - Transformaciones para Rendimiento, Consumo y Área](unidad_5.md)
- [Unidad 6 - Máquinas de Estado y Diseño Secuencial](unidad_6.md)

---

## 📎 Otros recursos

- [README general](README.md)
- [Planificación mensual](tareas_agosto_github_project.md)

---

> Todos los archivos están escritos en formato Markdown y pueden ser visualizados directamente en GitHub o VS Code.
"""

index_path = "/mnt/data/index.md"
with open(index_path, "w", encoding="utf-8") as f:
    f.write(index_md)

index_path
