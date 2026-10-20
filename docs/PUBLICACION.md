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

No necesitas transferir el dominio ni contratar otro alojamiento.

1. En el proyecto de Vercel abre Settings → Domains y agrega el dominio o subdominio elegido.
2. Copia los registros DNS exactos que Vercel muestre. El destino puede variar según el proyecto; no uses una IP de ejemplo.
3. Si Namecheap administra tus DNS, entra a Domain List → Manage → Advanced DNS → Host Records.
4. Para un subdominio como `plantas.tudominio.com`, normalmente crearás un CNAME con Host `plantas` y el Value que indique Vercel. Para el dominio raíz usa el registro que Vercel indique con Host `@`.
5. Si Vercel solicita un TXT de verificación, cópialo exactamente. Mantén los registros MX y TXT de correo y los de otros servicios. Cambia solo registros que entren en conflicto con el nombre que vas a usar.
6. Si los servidores DNS autoritativos pertenecen a otro proveedor, cambia los registros allí; Advanced DNS de Namecheap no controlará esos registros.
7. Espera a que Vercel confirme la configuración y emita HTTPS, y vuelve a probar la cámara desde el dominio.

No cambies los nameservers completos para esta conexión si puedes añadir los registros existentes. No se ha configurado ningún dominio hasta que Vercel y las consultas DNS confirmen los valores.
