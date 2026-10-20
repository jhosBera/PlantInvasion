# PlantInvasion

Una colección botánica pensada para el celular. Interfaz en español, categorías, fichas, siluetas bloqueadas y registro de fotos con almacenamiento local en el navegador.

## Desarrollo

Requiere Node.js 20.19+ o 22.12+.

```sh
npm ci
npm run dev
```

## Producción

```sh
npm run build
npm run preview
```

La cámara requiere HTTPS o localhost y permiso del usuario. También puedes seleccionar una imagen. Las fotos se comprimen y se guardan en localStorage; borrar los datos del navegador elimina la colección. Se incluyen tres especies iniciales de ejemplo. No hay cuentas ni sincronización.

**Identificación:** esta versión es una demostración con selección manual de especie; no analiza ni identifica la foto. La identificación automática requiere un servicio externo y un backend para proteger sus credenciales. No uses las fichas para decidir si una planta es comestible o medicinal.

Las fotografías del catálogo se cargan de Unsplash y las fuentes de Google Fonts; se requiere conexión para esos recursos. El álbum inicial contiene ocho especies. No representa un catálogo botánico exhaustivo.

## Publicación y dominio

Configurado para Vercel mediante `vercel.json`, sin backend ni servicios de pago. Consulta [la guía de publicación y Namecheap](docs/PUBLICACION.md). Publicar no habilita la identificación automática: sigue siendo un registro manual de demostración.
