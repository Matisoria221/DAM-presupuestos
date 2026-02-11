# Guía de Instalación - Aplicación Web DAM Presupuestos

## 🎉 ¡Mucho Más Fácil que Android Studio!

Esta es una **aplicación web** que funciona directamente en el navegador de tu teléfono o computadora. No necesitas Android Studio, compilar nada, ni conocimientos técnicos avanzados.

---

## 📱 Instalación en Android (Como App)

### Opción 1: Instalar desde el Navegador (Recomendado)

**Paso 1: Subir la App a Internet**

La forma más sencilla es usar **GitHub Pages** (gratis):

1. Ve a https://github.com
2. Crea una cuenta (si no tienes)
3. Haz clic en **"New repository"**
4. Nombre: `dam-presupuestos`
5. Marca **"Public"**
6. Haz clic en **"Create repository"**
7. Sube los archivos:
   - `index.html`
   - `manifest.json`
   - `sw.js`
8. Ve a **Settings** → **Pages**
9. En **Source** selecciona **"main"** → **Save**
10. Espera 2 minutos y tu app estará en: `https://TU-USUARIO.github.io/dam-presupuestos`

**Paso 2: Instalar en el Teléfono**

1. Abre **Chrome** en tu Android
2. Ve a la URL de tu app
3. Verás la aplicación funcionando
4. Toca el **menú de Chrome** (⋮)
5. Selecciona **"Agregar a pantalla de inicio"** o **"Instalar aplicación"**
6. Dale un nombre: "DAM Presupuestos"
7. ¡Listo! Ahora tendrás un ícono en tu pantalla principal

---

### Opción 2: Usar Localmente (Sin Internet)

**Paso 1: Preparar los Archivos**

1. Descarga los 3 archivos a tu computadora:
   - `index.html`
   - `manifest.json`
   - `sw.js`
2. Colócalos en una carpeta llamada `DAM-Presupuestos`

**Paso 2: Servir los Archivos**

**Método A - Python (Si lo tienes instalado):**

1. Abre la terminal/CMD en la carpeta
2. Ejecuta:
   ```bash
   python -m http.server 8000
   ```
3. Abre el navegador en: `http://localhost:8000`

**Método B - Live Server (Visual Studio Code):**

1. Descarga VS Code: https://code.visualstudio.com/
2. Instala la extensión "Live Server"
3. Abre la carpeta con los archivos
4. Clic derecho en `index.html` → "Open with Live Server"

**Método C - Simplemente Abrir el Archivo:**

1. Haz doble clic en `index.html`
2. Se abrirá en tu navegador
3. ⚠️ Algunas funciones pueden no funcionar (como PWA)

**Paso 3: Acceder desde el Teléfono**

Si usaste Python o Live Server:

1. Asegúrate de que tu teléfono y PC estén en la misma red WiFi
2. Averigua la IP de tu PC:
   - Windows: `ipconfig` en CMD → busca "IPv4"
   - Mac/Linux: `ifconfig` → busca "inet"
3. En el teléfono, abre Chrome y ve a: `http://TU-IP:8000`
4. Instala como en la Opción 1

---

## 💻 Usar en la Computadora

Simplemente:

1. Abre `index.html` en cualquier navegador moderno
2. ¡Ya funciona! Puedes:
   - Crear presupuestos
   - Agregar precios
   - Generar PDFs
   - Todo se guarda automáticamente en tu navegador

---

## ✨ Características de la App Web

✅ **No requiere instalación complicada**
✅ **Funciona sin conexión** (después de la primera carga)
✅ **Genera PDFs automáticamente**
✅ **Guarda todo en el teléfono** (LocalStorage)
✅ **Sistema de descuentos incluido**
✅ **Interfaz moderna y táctil**
✅ **Precios pre-cargados** (basados en tu PDF)
✅ **Se puede usar como app instalada**

---

## 📋 Cómo Usar la Aplicación

### 1. Primera Vez

Al abrir la app, ya tiene precios de ejemplo cargados (basados en el PDF de AAIERIC que compartiste). Puedes:

- **Agregar más precios** en la pestaña "Precios"
- **Editar los existentes** eliminándolos y agregando nuevos
- **Importar precios manualmente** desde tu lista

### 2. Crear un Presupuesto

**Tab "Nuevo Presupuesto":**

1. Completa los datos del cliente
2. Selecciona una categoría
3. Selecciona un ítem
4. Ingresa la cantidad
5. Presiona "Agregar Ítem"
6. Repite para más ítems
7. (Opcional) Agrega un descuento en %
8. Agrega observaciones
9. Presiona "Guardar Presupuesto"

### 3. Ver Presupuestos Guardados

**Tab "Guardados":**

- Ve la lista de todos tus presupuestos
- Presiona "Generar PDF" para descargar
- Presiona "Eliminar" para borrar uno

### 4. Gestionar Precios

**Tab "Precios":**

- Ve todos los precios cargados por categoría
- Agrega nuevos precios manualmente
- Elimina precios obsoletos

---

## 🔄 Actualizar Precios

### Método 1: Manual (Directamente en la App)

1. Ve a la pestaña **"Precios"**
2. Completa el formulario:
   - Categoría
   - Descripción
   - Precio
   - Unidad
3. Presiona "Agregar Precio"

### Método 2: Editar el Código

Si quieres cargar muchos precios a la vez:

1. Abre `index.html` en un editor de texto
2. Busca la función `cargarPreciosIniciales()`
3. Agrega tus precios en el array `preciosEjemplo`
4. Ejemplo:
```javascript
{categoria: 'Tu Categoría', descripcion: 'Tu Descripción', precio: 12345, unidad: 'ud'}
```
5. Guarda el archivo

---

## 📱 Compartir con Otros

### Método 1: Subir a Internet (Gratis)

Usa GitHub Pages como expliqué arriba. Todos podrán acceder con el link.

### Método 2: Enviar los Archivos

1. Comprime los 3 archivos en un ZIP
2. Envíalos por email/WhatsApp
3. La otra persona solo abre `index.html` en su navegador

### Método 3: Usar un Servicio como Netlify/Vercel

1. Crea cuenta en https://netlify.com (gratis)
2. Arrastra la carpeta con los archivos
3. Te dan un link permanente
4. Ejemplo: `dam-presupuestos.netlify.app`

---

## 🎨 Personalizar la App

### Cambiar el Logo/Nombre

Abre `index.html` y busca:

```html
<div class="header">
    <h1>DAM</h1>
    <p>Presupuestos de Instalaciones Eléctricas</p>
</div>
```

Cambia "DAM" por el nombre que quieras.

### Cambiar los Colores

Busca en `index.html` la sección `<style>` y cambia:

```css
.header {
    background: linear-gradient(135deg, #1976D2 0%, #1565C0 100%);
    /* Cambia estos códigos de color */
}
```

---

## 💾 ¿Dónde se Guardan los Datos?

Todos los datos se guardan en el **LocalStorage** del navegador:

- ✅ Los presupuestos
- ✅ Los precios
- ✅ Todo permanece aunque cierres el navegador

⚠️ **Importante**: Si borras los datos del navegador, perderás todo. Para hacer backup:

1. Ve a la consola del navegador (F12)
2. Copia el contenido de `localStorage`
3. Guárdalo en un archivo de texto

---

## 🔧 Solución de Problemas

### "No se genera el PDF"

**Solución:** Asegúrate de tener conexión a internet la primera vez (para descargar la librería jsPDF). Después funciona sin conexión.

### "Se borraron mis datos"

**Solución:** Los datos están en el LocalStorage del navegador. Si limpias los datos del navegador, se borran. Siempre exporta tus presupuestos a PDF.

### "No aparece el ícono en la pantalla"

**Solución:** Solo funciona si:
- La app está en un servidor (no solo abriendo el archivo)
- Usas Chrome o navegador compatible con PWA

---

## 🚀 Ventajas vs Android Studio

| Característica | App Web | Android Studio |
|---------------|---------|----------------|
| Instalación | ✅ Instantánea | ❌ Compleja |
| Compilación | ✅ No necesaria | ❌ Necesaria |
| Actualizaciones | ✅ Automáticas | ❌ Manual |
| Funciona en PC | ✅ Sí | ❌ Solo Android |
| Tamaño | ✅ ~100 KB | ❌ ~20 MB |
| Conocimientos | ✅ Básicos | ❌ Avanzados |

---

## 📞 Soporte

Si tienes problemas:

1. Verifica que estés usando un navegador moderno (Chrome, Firefox, Safari)
2. Asegúrate de que JavaScript esté habilitado
3. Prueba en modo incógnito
4. Revisa la consola del navegador (F12) para ver errores

---

## 🎯 Próximos Pasos

1. ✅ Descarga los archivos
2. ✅ Abre `index.html` en tu navegador
3. ✅ ¡Empieza a crear presupuestos!
4. 📤 (Opcional) Sube a GitHub Pages para acceso online
5. 📱 (Opcional) Instala como app en tu teléfono

---

**¡Es tan fácil como abrir un archivo HTML!** 🎉

No necesitas aprender Android Studio ni compilar nada. Esta solución es perfecta para empezar rápidamente.
