# Demo: presentaciones como código con Marp

![](./images/1.png)

Proyecto listo para probar una presentación de Docker hecha con:

- Markdown
- Marp
- Marp CLI
- Marp for VS Code / Kiro
- Git

## Estructura

```text
marp-kiro-docker-final/
├── docker.md
├── docker.css
├── .marprc.yml
├── README.md
├── images/
└── .vscode/
    └── settings.json
```

## Requisitos

- Node.js 18+ recomendado
- `npx`
- Kiro o VS Code
- Extensión **Marp for VS Code**

## Instalar / probar Marp CLI

```bash
npx @marp-team/marp-cli --version
```

No hace falta instalarlo globalmente.

## Preview

1. Abrí la carpeta completa en Kiro o VS Code.
2. Instalá **Marp for VS Code**.
3. Abrí `docker.md`.
4. Abrí el Markdown Preview.
5. Si el tema no aparece:

```text
Developer: Reload Window
```

## Exportar HTML

```bash
npx @marp-team/marp-cli docker.md -o docker.html
```

## Exportar PDF

```bash
npx @marp-team/marp-cli docker.md --pdf
```

## Exportar PPTX

```bash
npx @marp-team/marp-cli docker.md --pptx
```

## Demo de nginx

```bash
docker run -d \
  --name web \
  -p 8080:80 \
  nginx
```

Abrí:

```text
http://localhost:8080
```

Limpiar:

```bash
docker rm -f web
```

## Prompt para crear la presentación con Kiro

```text
Quiero crear una presentación técnica utilizando Marp.

Tema:
Introducción a Docker.

Audiencia:
Personas que nunca utilizaron contenedores.

Duración:
20 minutos.

Objetivo:
Que al finalizar puedan explicar:
- qué es una imagen
- qué es un contenedor
- cómo ejecutar su primer docker run

Creá un archivo llamado `docker.md`.

Requisitos:
- usar Markdown compatible con Marp
- formato 16:9
- aproximadamente 10 slides
- una idea principal por slide
- máximo 5 bullets por slide
- evitar párrafos largos
- incluir diagramas simples cuando ayuden
- incluir comandos ejecutables
- incluir una demo con nginx
- cerrar con 3 conceptos clave

El archivo debe comenzar con:

---
marp: true
paginate: true
size: 16:9
---

Generá únicamente el contenido completo de `docker.md`.
```

## Prompt para crear el tema CSS

```text
Creá un tema personalizado para Marp
y guardalo en un archivo llamado `docker.css`.

El archivo debe comenzar exactamente con:

/* @theme docker */

Objetivo:
Crear un diseño técnico, minimalista y moderno
para una presentación introductoria sobre Docker.

Requisitos visuales:
- pensado para formato 16:9
- paleta inspirada en Docker
- fondo claro
- alto contraste
- títulos grandes y visibles
- tipografía legible desde una sala
- máximo foco en claridad
- buen espaciado entre elementos
- tablas fáciles de leer
- bullets simples
- bloques de código con estilo de terminal
- código suficientemente grande para proyectar
- portada visualmente distinta
- estilos consistentes para h1, h2, listas, tablas y código

No agregues JavaScript.
No generes HTML.
No modifiques `docker.md`.

Generá únicamente el contenido completo de `docker.css`.
```

## Prompt de revisión

```text
Revisá `docker.md`.

Objetivo:
Hacer la presentación más clara y visual.

Aplicá estas reglas:
- máximo 4 bullets por slide
- una idea principal por slide
- reducir frases largas
- eliminar repeticiones
- mantener todos los comandos de terminal
- conservar las demos
- conservar la estructura general
- no agregar conceptos nuevos

Modificá directamente `docker.md`.
```

## Sobre la slide de arquitectura

La arquitectura se construye con HTML + CSS dentro de Marp para evitar diagramas ASCII difíciles de leer.

El flujo muestra:

```text
Developer → Docker CLI → Docker Engine

Images ⇄ Docker Hub → Containers
```

Todo sigue siendo editable y versionable como código.

---

**Crear presentaciones también puede sentirse como programar. 🚀**
# roxs-presentation-as-code
