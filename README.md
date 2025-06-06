# 🌍 Wispok I18n — Sistema de traducciones

Este repositorio centraliza los archivos de traducción utilizados en los distintos proyectos de Wispok. Las traducciones están organizadas por proyecto y por idioma, y son servidas mediante [jsDelivr CDN](https://www.jsdelivr.com/).

---

## 📁 Estructura del repositorio

```json
/locales/
├── checkout-generico/
│ ├── es/
│ │ └── translation.json
│ ├── en/
│ │ └── translation.json
│ └── languages.json
├── checkout-sonigas/
│ ├── es/
│ ├── en/
│ └── languages.json
└── ...
```

---

## ➕ Cómo añadir un nuevo idioma

1. **Ubica el proyecto** dentro de `/locales`, por ejemplo: `checkout-generico`.
2. **Agrega una nueva carpeta con el código de idioma ISO 639-1**, por ejemplo `fr/`.
3. Dentro de la carpeta, crea un archivo `translation.json` con las traducciones:

```json
{
	"form.title": "Entrez votre adresse e-mail",
	"form.submit": "Envoyer"
}
```

Actualiza el archivo languages.json del proyecto para incluir el nuevo idioma:

```json
[
	{ "code": "es", "label": "Español" },
	{ "code": "en", "label": "English" },
	{ "code": "fr", "label": "Français" }
]
```

---

## 🧼 Cómo purgar caché de jsDelivr

jsDelivr cachea automáticamente los archivos, por lo que los cambios pueden tardar hasta 24 horas en propagarse si no se hace una limpieza manual.

### 🧽 Pasos para purgar una ruta:

1. Ve a la herramienta oficial:
   👉 https://www.jsdelivr.com/tools/purge
2. Ingresa la URL completa del recurso que deseas purgar, por ejemplo:

```
https://cdn.jsdelivr.net/gh/wispok/wispok-i18n@main/locales/checkout-generico/es/translation.json
```

3. Haz clic en **Purge Now**.

Esto forzará a jsDelivr a invalidar el archivo y servir la versión más reciente desde GitHub.
