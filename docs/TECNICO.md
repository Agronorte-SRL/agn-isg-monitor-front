# agn-isg-monitor-front — Documentación técnica

## Resumen
- **Qué es:** frontend Angular del "Monitor ISG": seguimiento de máquinas conectadas de clientes (alertas, paquetes ISG, atención/derivaciones, gestión y coordinación de servicios, performance y administración).
- **Estado:** legado (1 commit, diciembre 2024).
- **Autor principal:** matiasagronorte (1 commit).
- **Último commit:** 2024-12-31 — "main".

## Stack
Angular (standalone components) + TypeScript. Rutas en `src/app/app.routes.ts`: `monitor`, `home`, `alertas`, `paquetes`, `atencion`, `servicios`, `coordinacion_servicios`, `maquinas`, `account`, `admin` y `performance` (estas dos con guard de admin), `auth`.

Archivos sueltos en la raíz: `FIELD OPERATION.json`, `MEDIDAS DE FIELD OPERATION.json`, `MEDIDAS FIELD OPS.xlsx`, `convert.py`, `data.php`, `prueba.html` (pruebas con datos de John Deere Field Operations).

## Sistemas conectados
Configurado en `src/app/appsettings.ts`:
- `API_ENDPOINT`: backend PHP en `http://192.168.2.109:9090/backend/interface` (ver `agn-common-backend-nd`).
- `API_ISG_AGRONORTE`: `http://192.168.2.109:9090/isg_agronorte`.
- Comprobantes y archivos de clientes servidos desde el mismo host.

## Cómo se corría
`npm install` y `ng serve` (dev) / `ng build` y publicar `dist/` en el servidor web. Dónde estaba publicado: No determinado.

## Observaciones
- **Token de API hardcodeado** en `src/app/appsettings.ts` (`REQUEST_TOKEN`). Rotarlo en el backend.
- Backend apuntado por IP interna y HTTP sin TLS.

## Recomendación
**Archivar**: un solo commit de diciembre 2024 sin cambios posteriores; su backend (`agn-common-backend-nd`) también es legado.