### Enlaces

```markdown
[Texto del enlace](https://ejemplo.com)
[Enlace con título](https://ejemplo.com "Título")
<https://enlace-automatico.com>
```

## Obsidian Flavored Markdown (OFM)

### Enlaces internos

```markdown
[[Nombre de la nota]]
[[Nombre de la nota|Texto personalizado]]
[[Nombre de la nota#Encabezado]]
[[Nombre de la nota#Encabezado|Texto personalizado]]
```

### Referencias a bloques

```markdown
Texto normal ^block-id

[[Nota#^block-id]] // Enlace al bloque específico
![[Nota#^block-id]] // Embebe el bloque específico
```

## Imágenes

```markdown
![Texto alternativo](ruta/imagen.jpg)
![Texto alternativo](ruta/imagen.jpg "Título de la imagen")

// En Obsidian también puedes usar:
![[imagen.jpg]]
![[imagen.jpg|300]] // Con ancho específico
![[imagen.jpg|300x200]] // Con dimensiones específicas}
![[imagen.jpg|x200]] // Solo altura de 200px
```

### Embebidos

```markdown
![[Otra nota]] // Embebe toda la nota
![[Otra nota#Sección]] // Embebe solo una sección
![[imagen.jpg]] // Embebe imagen
![[documento.pdf]] // Embebe PDF
![[audio.mp3]] // Embebe audio
![[video.mp4]] // Embebe video
```

### Tareas

```markdown
- [ ] Tarea pendiente
- [x] Tarea completada
- [!] Tarea importante
- [?] Tarea con pregunta
- [-] Tarea cancelada
- [>] Tarea reprogramada
- [<] Tarea programada
```

### Tags

```markdown
#tag
#tag/subtag
#tag-con-guiones
#tag_con_guiones_bajos
```

### Footnotes

```markdown
Texto con referencia[^1]
Otra referencia[^nota-personalizada]

[^1]: Esta es la nota al pie
[^nota-personalizada]: Nota al pie con ID personalizado
```

### **Comentarios**

```markdown
%% Este es un comentario que no se muestra en vista previa %%
```

### Callouts

```markdown
> [!note]
> Esta es una nota básica

> [!example]
> Ejemplo de algo

> [!tip] Título personalizado
> Este es un consejo

> [!info]
> Información adicional

> [!warning]
> Esta es una advertencia

> [!error]
> Este es un error

> [!quote]
> Esta es una cita especial

> [!abstract]
> Resumen o abstract

> [!todo]
> Lista de tareas pendientes

> [!question]
> Pregunta o FAQ
```
### Callouts plegables

```markdown
> [!note]- Callout colapsado por defecto
> Este contenido está oculto inicialmente

> [!tip]+ Callout expandido por defecto
> Este contenido está visible inicialmente
```

### Metadatos YAML

```markdown
---
title: "Título de la nota"
tags: [tag1, tag2, tag3]
author: "Tu nombre"
date: 2025-01-15
aliases: [alias1, alias2]
---

Contenido de la nota...
```