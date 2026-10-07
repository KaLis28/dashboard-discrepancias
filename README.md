# Dashboard de Discrepancias

Dashboard web para GitHub Pages conectado al Excel corporativo de SharePoint.

## Características
- Usa únicamente la hoja **Discrepancias**.
- No usa la hoja GHV.
- No muestra ni procesa Responsable / Reportado por.
- Filtros: Año, Mes, Semana, Área, Tipo de contrato, Tipo de error y Trim.
- KPIs, tendencia semanal, discrepancias por área, top de tipos de error y tabla detallada.
- Revisión automática de SharePoint cada 30 segundos.
- Solo vuelve a leer la hoja cuando cambia el eTag del archivo.
- Los datos no están embebidos en el repositorio.

## Configuración Microsoft Entra
1. Ir a https://entra.microsoft.com
2. App registrations > New registration.
3. Nombre sugerido: Dashboard Discrepancias.
4. Seleccionar "Accounts in this organizational directory only".
5. Authentication > Add a platform > Single-page application.
6. Agregar como Redirect URI:
   https://kalis28.github.io/dashboard-discrepancias/
7. API permissions > Microsoft Graph > Delegated permissions > Files.Read.All.
8. Copiar el Application (client) ID.
9. Reemplazar en config.js:
   REEMPLAZA_CON_CLIENT_ID_DE_ENTRA_ID

Si la empresa exige aprobación administrativa para Files.Read.All, TI debe aprobarla.

## Publicar con GitHub Pages
En el repositorio:
Settings > Pages > Source: Deploy from a branch > Branch: main > /(root) > Save

La URL será:
https://kalis28.github.io/dashboard-discrepancias/

La página puede ser pública, pero los datos de SharePoint requieren iniciar sesión con Microsoft y permiso sobre el Excel.
