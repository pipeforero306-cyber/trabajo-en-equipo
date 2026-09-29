# Reto 3: Fuga de información

> **Caso de ciberseguridad:** un antiguo colaborador se llevó el diseño del nuevo producto.

**Integrantes:** Rubén · Pau · Alex · Daniel

---

## ¿Qué ha pasado?

Una empresa de ingeniería, con oficina, Wi-Fi corporativo y colaboradores que trabajan en remoto, lleva seis meses desarrollando el diseño de un nuevo producto.

Justo antes de su lanzamiento, una startup presenta un diseño idéntico. La investigación muestra que antiguos colaboradores todavía tenían acceso remoto porque sus permisos no se revocaron al finalizar su relación con la empresa. Los registros de acceso, respaldados mediante copias de seguridad, permiten identificar al usuario y el momento en que se produjo la copia.

---

## Fallos detectados

- **Accesos remotos no revocados:** antiguos colaboradores conservaron permisos de acceso.
- **Información confidencial sin cifrar:** existía un procedimiento, pero no se aplicaba de forma efectiva.
- **Falta de coordinación:** RRHH, la gestoría y el área informática no compartían un proceso de bajas.
- **Rotación de colaboradores externos:** hubo numerosos cambios durante el año sin una revisión suficiente de cuentas y permisos.
- **Aspectos positivos:** los logs estaban activos, tenían copias de seguridad y se habían firmado acuerdos de confidencialidad.

---

## Aportaciones del equipo

| Integrante | Propuestas principales |
|---|---|
| Rubén | Retirar accesos a ex-trabajadores, coordinar RRHH con informática y entregar los datos personales por un canal controlado. |
| Pau | Aplicar un protocolo de baja inmediato y valorar acciones legales contra el ex-colaborador y la empresa receptora si conocía el origen ilícito de la información. |
| Alex | Mejorar el cifrado como capa de protección y desactivar o eliminar usuarios inactivos de forma continuada. |
| Daniel | Automatizar la revocación de acceso, avisar a administradores y comunicar el incidente a RRHH. |

---

## Medidas de prevención

1. **Revocar los accesos de inmediato** al producirse una baja. No debe existir un margen de 24 horas con acceso activo.
2. **Automatizar el offboarding:** la baja comunicada por RRHH debe generar una tarea registrada para Sistemas y revocar cuentas, VPN, correo, aplicaciones SaaS, sesiones, tokens, claves API y credenciales compartidas.
3. **Aplicar el principio de mínimo privilegio:** cada usuario debe tener solo los permisos imprescindibles para realizar su trabajo.
4. **Usar MFA:** habilitar autenticación multifactor para VPN, correo, repositorios, almacenamiento y aplicaciones críticas.
5. **Cifrar la información confidencial:** proteger los datos almacenados y transmitidos, y custodiar correctamente las claves de cifrado.
6. **Auditar usuarios y permisos:** revisar periódicamente cuentas activas, privilegios, colaboradores externos y accesos administrativos.
7. **Monitorizar y conservar logs:** mantener registros centralizados, protegidos y con copias de seguridad; revisar alertas relacionadas con descargas o copias inusuales.
8. **Formalizar la salida:** recordar las obligaciones de confidencialidad y exigir la devolución o eliminación de la información corporativa por un procedimiento verificable.

---

## Respuesta ante el incidente

1. **Contener:** bloquear cuentas, sesiones y accesos sospechosos; revocar permisos y rotar contraseñas, tokens, claves API y secretos compartidos.
2. **Preservar pruebas:** conservar logs, copias de seguridad, correos, dispositivos y cualquier evidencia, respetando su integridad y trazabilidad.
3. **Investigar:** identificar qué información se copió, por quién, cuándo, desde dónde y si se transfirió a terceros.
4. **Coordinar internamente:** informar a dirección, RRHH, responsables de seguridad, sistemas y asesoría jurídica.
5. **Evaluar datos personales:** comprobar si la fuga incluye datos personales y el riesgo que puede causar a las personas afectadas.
6. **Documentar:** registrar las decisiones, evidencias, medidas adoptadas y la evaluación de riesgos.

---

## Vía legal y protección de datos

Los acuerdos de confidencialidad firmados y los logs pueden servir de base probatoria. En España, la **Ley 1/2019 de Secretos Empresariales** protege información que sea secreta, tenga valor empresarial por ser secreta y haya sido objeto de medidas razonables de protección. La obtención, utilización o revelación sin consentimiento puede ser ilícita.

Si el incidente afecta a **datos personales**, la organización debe valorar la notificación de la brecha a la autoridad de control. Cuando la brecha pueda suponer un riesgo para los derechos y libertades de las personas, el RGPD exige notificarla sin dilación indebida y, cuando sea posible, dentro de las 72 horas posteriores a tener conocimiento. Aunque no sea necesario notificarla, debe documentarse la evaluación y la decisión tomada.

La fuga puede generar pérdidas económicas, pérdida de ventaja competitiva, daño reputacional, pérdida de confianza de clientes o inversores y posibles responsabilidades contractuales, civiles o penales, según los hechos.

---

## Conclusión

La fuga se podía haber evitado mediante un proceso de baja claro, coordinado y automatizado. El cifrado, los logs y los acuerdos de confidencialidad son importantes, pero solo resultan eficaces si se aplican de forma constante.

**Recomendación final:** revocación inmediata de accesos, proceso de offboarding automatizado, auditorías periódicas y entrega de datos personales exclusivamente por un canal controlado.

---

## Fuentes

- [AEPD — Notificación de brechas de datos personales](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/brechas-de-datos-personales-notificacion)
- [BOE — Ley 1/2019, de Secretos Empresariales](https://www.boe.es/buscar/doc.php?id=BOE-A-2019-2364)
- [ENISA — Insider Threat](https://www.enisa.europa.eu/sites/default/files/publications/ETL2020%20-%20Insider-Threat%20A4.pdf)
