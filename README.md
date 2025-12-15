# ⛽ GasFinder Pro

**GasFinder Pro** es una aplicación nativa de Android diseñada para ayudar a los conductores a localizar las gasolineras más económicas utilizando datos en tiempo real de una API pública estatal. Además de comparar precios, la app ofrece un ecosistema de fidelización que permite canjear cupones y gestionar servicios de lavado de coches.

---

## 📋 Tabla de Contenidos
- [Características](#-características)
- [Tecnologías](#-tecnologías)
- [Arquitectura](#-arquitectura)
- [Instalación y Configuración](#-instalación-y-configuración)
- [Uso](#-uso)
- [Contribución](#-contribución)
- [Licencia](#-licencia)
- [Contacto](#-contacto)

---

## 🚀 Características

### 🔍 Comparador de Precios
- Conexión a **API Pública del Estado** para obtener precios actualizados de combustible.
- Filtrado por tipo de combustible (Gasolina 95, 98, Diesel, GLP, etc.).
- Ordenamiento por precio (del más bajo al más alto) y cercanía.

### 📍 Mapas y Geolocalización
- Visualización de gasolineras en **Google Maps**.
- Indicadores visuales de precios (verde para económico, rojo para costoso).

### 👤 Usuarios y Fidelización (Firebase)
- **Login/Registro:** Autenticación segura vía correo electrónico o Google.
- **Cupones:** Sistema para visualizar y canjear cupones de descuento exclusivos en la app.
- **Lavado de Coches:**
  - Identificación de gasolineras con túnel de lavado.
  - Compra y canje de fichas/tickets digitales de lavado.
  - Historial de lavados realizados.

---

## 🛠 Tecnologías

El proyecto está construido utilizando el ecosistema moderno de Android:

- **Lenguaje:** [Kotlin](https://kotlinlang.org/)
- **Entorno:** Android Studio Hedgehog o superior.
- **Backend as a Service (BaaS):** [Firebase](https://firebase.google.com/)
  - *Authentication:* Gestión de usuarios.
  - *Firestore Database:* Almacenamiento de perfiles, cupones y transacciones de lavado.
- **Mapas:** Google Maps SDK for Android.
- **Red:** Retrofit + OkHttp (para consumo de API REST pública).
- **Inyección de Dependencias:** Hilt / Koin (según implementación).
- **Carga de Imágenes:** Glide / Coil.

---

## 🏗 Arquitectura

La aplicación sigue el patrón **MVVM (Model-View-ViewModel)** recomendado por Google, asegurando un código limpio, escalable y testeable.

- **Data Layer:** Repositorios que gestionan datos locales y remotos (API del Estado + Firebase).
- **Domain Layer:** Casos de uso y lógica de negocio (reglas de cupones, filtrado de precios).
- **UI Layer:** Activities/Fragments o Jetpack Compose observando LiveData/StateFlow.

---

## 💻 Instalación y Configuración

Sigue estos pasos para ejecutar el proyecto en tu entorno local.

### Prerrequisitos
- Android Studio instalado.
- JDK 11 o superior.
- Cuenta de Google para configurar Firebase.

### 1. Clonar el repositorio
```bash
git clone [https://github.com/abenper/ProyectoFinalDAM2.git](https://github.com/abenper/ProyectoFinalDAM2.git)
cd GasFinderPro
```

### 2. Configuración de Firebase
1. Ve a la [Consola de Firebase](https://console.firebase.google.com/).
2. Crea un nuevo proyecto llamado `GasFinderPro`.
3. Añade una app Android con el nombre de paquete de este proyecto (ej: `com.ejemplo.gasfinder`).
4. Descarga el archivo `google-services.json`.
5. Mueve el archivo a la carpeta `app/` de tu proyecto:
   `GasFinderPro/app/google-services.json`.
6. Habilita **Authentication** y **Cloud Firestore** en la consola.

### 3. Configuración de API Keys
Necesitas una API Key de Google Maps.
1. Crea un archivo `secrets.properties` en la raíz (si no existe) o configúralo en tu `local.properties`.
2. Añade tu clave:
```properties
MAPS_API_KEY=tu_clave_de_api_aqui
```
*Nota: Asegúrate de que el `AndroidManifest.xml` lea esta variable.*

### 4. Ejecutar
Abre el proyecto en Android Studio, espera a que Gradle sincronice y presiona **Run** ▶️.

---

## 🤝 Contribución

¡Las contribuciones son bienvenidas! Si tienes una idea para mejorar el sistema de cupones o la visualización del mapa:

1. Haz un Fork del proyecto.
2. Crea una rama para tu feature (`git checkout -b feature/NuevaFuncionalidad`).
3. Haz Commit de tus cambios (`git commit -m 'Añadida nueva funcionalidad'`).
4. Haz Push a la rama (`git push origin feature/NuevaFuncionalidad`).
5. Abre un Pull Request.

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.

