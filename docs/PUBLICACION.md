# Publicar PlantInvasion sin contratar servicios de pago

La versión actual es una demostración: álbum, fotos y selección manual de especie. La identificación automática y la sincronización entre dispositivos todavía no están implementadas. Publicar en Vercel no añade esas funciones.

## Vercel

Usa una cuenta personal con el plan Hobby si tu uso cumple sus condiciones. No actives complementos de pago. Este proyecto es estático: no requiere base de datos, funciones de pago ni variables secretas. Los límites y las condiciones del plan pueden cambiar; revisa los que muestra tu cuenta.

1. Entra en https://vercel.com/new e inicia sesión con tu GitHub.
2. Importa `jhosBera/PlantInvasion`. Si no aparece, concede a la integración de Vercel acceso a ese repositorio.
3. Usa la raíz del repositorio como Root Directory y `main` como Production Branch.
4. El archivo `vercel.json` configura Vite, `npm ci --no-audit --no-fund`, `npm run build` y la carpeta de salida `dist`.
5. Pulsa Deploy y abre la URL que Vercel asigne al proyecto. El nombre exacto depende de su disponibilidad.
6. Comprueba en el celular que se muestran las ocho especies, se pueden filtrar, una foto se guarda eligiendo la especie y el álbum se conserva al recargar el mismo navegador.

Las siguientes actualizaciones enviadas a `main` se publicarán mediante la integración de GitHub una vez conectada. La cámara requiere HTTPS y permiso del navegador; elegir una foto es la alternativa.

## Dominio de Namecheap

El subdominio elegido es **plantinvasion.beraun.space** (dominio base: `beraun.space`). Las mayúsculas no cambian un nombre DNS.

En Vercel agrega `plantinvasion.beraun.space` en Settings → Domains del proyecto. Si los servidores DNS de `beraun.space` están gestionados por Namecheap, añade en Advanced DNS → Host Records:

| Campo | Valor |
| --- | --- |
| Type | CNAME Record, si es el tipo indicado por Vercel |
| Host | `plantinvasion` |
| Value / Target | El destino exacto mostrado por Vercel para este proyecto; pendiente de obtener |
| TTL | Automatic |

No pongas `plantinvasion.beraun.space` completo en el campo Host de Namecheap, que añade el dominio base. No uses una IP ni un destino de ejemplo. Si Vercel pide un registro TXT de verificación, añade también los valores que indique. Mantén los registros de `@`, `www` y correo.

Esta documentación prepara la conexión; no confirma que el proyecto esté desplegado ni que los registros DNS se hayan aplicado. La consulta DNS desde el entorno no pudo completarse, por lo que no se ha determinado si ya existen registros para ese subdominio.

No necesitas transferir el dominio ni contratar otro alojamiento.

1. En el proyecto de Vercel abre Settings → Domains y agrega el dominio o subdominio elegido.
2. Copia los registros DNS exactos que Vercel muestre. El destino puede variar según el proyecto; no uses una IP de ejemplo.
3. Si Namecheap administra tus DNS, entra a Domain List → Manage → Advanced DNS → Host Records.
4. Para un subdominio como `plantas.tudominio.com`, normalmente crearás un CNAME con Host `plantas` y el Value que indique Vercel. Para el dominio raíz usa el registro que Vercel indique con Host `@`.
5. Si Vercel solicita un TXT de verificación, cópialo exactamente. Mantén los registros MX y TXT de correo y los de otros servicios. Cambia solo registros que entren en conflicto con el nombre que vas a usar.
6. Si los servidores DNS autoritativos pertenecen a otro proveedor, cambia los registros allí; Advanced DNS de Namecheap no controlará esos registros.
7. Espera a que Vercel confirme la configuración y emita HTTPS, y vuelve a probar la cámara desde el dominio.

No cambies los nameservers completos para esta conexión si puedes añadir los registros existentes. No se ha configurado ningún dominio hasta que Vercel y las consultas DNS confirmen los valores.
