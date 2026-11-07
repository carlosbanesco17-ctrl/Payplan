# PayPlan

Aplicación web progresiva para organizar deudas, vencimientos y pagos. No realiza transacciones financieras: los registros son manuales y se guardan localmente en el navegador.

## Publicar en GitHub Pages

1. Abre **Settings → Pages** en este repositorio.
2. En **Build and deployment**, elige **Deploy from a branch**.
3. Selecciona la rama `main` y la carpeta `/(root)`; pulsa **Save**.
4. Espera a que termine el despliegue y abre la URL HTTPS que muestra Pages.
5. En Android/Chrome, abre esa URL y selecciona **Instalar aplicación** o **Añadir a pantalla de inicio**. En iPhone/iPad, usa **Compartir → Añadir a pantalla de inicio**.

Los archivos de la PWA (`index.html`, `manifest.json`, `service-worker.js` e `icon.svg`) deben permanecer juntos en la raíz del sitio. El icono SVG incluido evita tener que crear archivos de imagen adicionales.

## Funciones

- Deudas con categoría, saldo, fecha y nota.
- Orden de vencimientos, progreso, puntos e historial de pagos.
- Perfil y selección de moneda.
- Recordatorios del navegador cuando la app está abierta y el navegador los permite.
- Exportación e importación manual de respaldo JSON.
- Caché de la app para que el shell cargue sin conexión después de la primera visita.

## Límites importantes

- Los datos se guardan en el almacenamiento local de ese navegador/dispositivo; no hay cuenta, sincronización ni recuperación automática.
- El service worker permite almacenar la interfaz, pero no puede realizar pagos ni garantizar recordatorios con la app cerrada. Las notificaciones push en segundo plano requieren un servicio de backend.
- Para transferir datos, descarga un respaldo desde Perfil y luego impórtalo en el otro navegador/dispositivo.
