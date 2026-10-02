---
marp: true
theme: docker
paginate: true
size: 16:9
---

<!-- _paginate: false -->
<!-- _class: lead -->

# 🐳 Introducción a Docker

## De cero a tu primer contenedor

Presentación creada con **Markdown + Marp**

---

## El problema: "funciona en mi máquina" 😅

- Distintas versiones de librerías
- Dependencias que chocan entre proyectos
- Configuraciones diferentes
- En desarrollo funciona, en producción no

```text
Dev 💻   →   ✅ funciona
Prod 🖥️  →   ❌ se rompe
```

---

## ¿Qué es Docker?

Docker permite empaquetar una aplicación junto con sus dependencias para ejecutarla de forma consistente.

```text
Aplicación
    +
Dependencias
    ↓
Imagen Docker
    ↓
Contenedor
```

---

## ¿Qué es una imagen?

- Plantilla de **solo lectura**
- Incluye código, librerías y configuración
- Se utiliza para crear contenedores

```text
imagen = molde / receta 📦
```

---

## ¿Qué es un contenedor?

- Una **imagen en ejecución**
- Aislado
- Portable
- Descartable

```text
contenedor = aplicación corriendo ▶️
```

---

## Imagen vs Contenedor

| Imagen | Contenedor |
|---|---|
| Estática | En ejecución |
| Solo lectura | Lectura/escritura |
| Molde | Instancia |

```text
1 imagen  →  N contenedores
```

---

## Nuestro primer contenedor

```bash
docker run hello-world
```

Docker:

1. Busca la imagen localmente
2. La descarga si no existe
3. Crea el contenedor
4. Ejecuta el proceso

---

## Demo: nginx

```bash
docker run -d \
  --name web \
  -p 8080:80 \
  nginx
```

<div class="demo-actions">

  <div class="demo-action">
    <span class="demo-action-icon">🌐</span>
    <div>
      <strong>Abrí en el navegador</strong>
      <code>http://localhost:8080</code>
    </div>
  </div>

  <div class="demo-action">
    <span class="demo-action-icon">🧹</span>
    <div>
      <strong>Al terminar</strong>
      <code>docker rm -f web</code>
    </div>
  </div>

</div>

---

## Arquitectura básica de Docker

<div class="docker-arch-top">

  <div class="arch-card">
    <div class="arch-icon">👩‍💻</div>
    <strong>Developer</strong>
    <span>ejecuta comandos</span>
  </div>

  <div class="arch-arrow">→</div>

  <div class="arch-card">
    <div class="arch-icon">⌨️</div>
    <strong>Docker CLI</strong>
    <span>docker run / build / pull</span>
  </div>

  <div class="arch-arrow">→</div>

  <div class="arch-card arch-main">
    <div class="arch-icon">🐳</div>
    <strong>Docker Engine</strong>
    <span>construye y ejecuta</span>
  </div>

</div>

<div class="docker-arch-bottom">

  <div class="arch-card arch-soft">
    <div class="arch-icon">📦</div>
    <strong>Images</strong>
    <span>plantillas</span>
  </div>

  <div class="arch-arrow">⇄</div>

  <div class="arch-card arch-hub">
    <div class="arch-icon">☁️</div>
    <strong>Docker Hub</strong>
    <span>registry</span>
  </div>

  <div class="arch-arrow">→</div>

  <div class="arch-card arch-soft">
    <div class="arch-icon">▶️</div>
    <strong>Containers</strong>
    <span>apps en ejecución</span>
  </div>

</div>

---

## 3 conceptos para llevarte 🚀

1. **Imagen** → el molde
2. **Contenedor** → la imagen ejecutándose
3. **docker run** → crea y ejecuta un contenedor

```bash
docker run hello-world
```

**Próximo paso:** probalo vos.
