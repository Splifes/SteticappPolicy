# Política de Privacidad — Steticapp

**Última actualización:** 27 de enero de 2025

---

## 1. Quiénes somos

**Steticapp** («la aplicación», «nosotros», «nuestro») es una aplicación móvil de gestión para profesionales de estética, centros de belleza y clínicas estéticas. Permite gestionar pacientes, turnos, tratamientos, equipos y estadísticas, con soporte offline y sincronización en tiempo real.

- **Nombre de la aplicación:** Steticapp  
- **Desarrollador / responsable del tratamiento:** [Nombre o razón social del desarrollador — **reemplazar**]  
- **Contacto:** [email de privacidad/soporte — **reemplazar**]

---

## 2. Alcance

Esta política describe qué datos personales recopilamos, para qué los usamos, dónde se almacenan, con quién se comparten (si aplica), cuánto tiempo se conservan y qué derechos tiene el usuario. Es aplicable a quienes utilizan la aplicación Steticapp en Android e iOS.

---

## 3. Datos que recopilamos

Recopilamos los datos que se detallan a continuación, agrupados por categoría y según su origen.

### 3.1 Datos que usted nos proporciona

| Dato | Finalidad | Dónde se almacena |
|------|-----------|-------------------|
| **Email** | Cuenta de usuario, autenticación y recuperación de sesión | Dispositivo (SharedPreferences), Firebase Authentication, Firebase Realtime Database |
| **Contraseña** | Autenticación (almacenada de forma local para “recordar sesión”) | Dispositivo (SharedPreferences) — véase nota en sección 10 |
| **Nombre y apellido** | Identificación del usuario y del perfil en la estética | Dispositivo, Firebase Realtime Database |
| **Datos de pacientes** (nombre, apellido, teléfono, email, fecha de nacimiento, género, observaciones, redes sociales, historial de tratamientos sugeridos) | Gestión de fichas de pacientes y turnos en la estética | Firebase Realtime Database (por estética), dispositivos con la app (caché/offline) |
| **Datos de turnos** (paciente asociado, fecha/hora, operador, método de pago, descuentos, observaciones, etc.) | Gestión de agenda y estadísticas | Firebase Realtime Database, cola offline y logs locales (véase 3.3) |
| **Datos de la estética** (nombre, tipo, descripción, códigos de invitación, miembros y roles) | Funcionamiento multi‑estética y equipos | Firebase Realtime Database, dispositivo (estética actual, preferencias) |

### 3.2 Datos que genera o recopila el sistema

| Dato | Finalidad | Dónde se almacena |
|------|-----------|-------------------|
| **Identificador único de usuario (UID)** | Vinculación de datos a la cuenta en Firebase Auth | Firebase, dispositivo |
| **Identificador de estética actual** | Saber en qué estética trabaja el usuario en la sesión | Dispositivo (SharedPreferences) |
| **Acciones pendientes de sincronización** (crear/actualizar/eliminar turnos, pacientes, etc.) | Funcionamiento offline y sincronización posterior | Dispositivo (SharedPreferences, backups locales en `queue_backups`) |
| **Logs de acciones** (tipo de acción, tipo de entidad, ID, nombre de entidad, ID/usuario, descripción, metadatos) | Diagnóstico y trazabilidad de operaciones | Solo en el dispositivo (carpeta SteticappLogs / directorio de documentos de la app) |

### 3.3 Datos de uso y técnicos (terceros)

| Dato / Servicio | Finalidad | Proveedor |
|-----------------|-----------|-----------|
| **Firebase Authentication** | Crear y mantener la sesión (email/contraseña) | Google (Firebase) |
| **Firebase Realtime Database** | Almacenar usuarios, estéticas, pacientes, turnos, tratamientos y códigos de invitación | Google (Firebase) |
| **Conexión a Internet** | Verificar conectividad para modo offline/online | Solo uso local (connectivity_plus); no se envía a servidor propio |

**Nota:** En el código actual **no** están integrados Firebase Analytics, Firebase Crashlytics ni Firebase Cloud Messaging. Si en el futuro se añaden, esta política deberá actualizarse y, en su caso, recabarse consentimiento según la normativa aplicable.

---

## 4. Cómo usamos sus datos

Utilizamos los datos para:

- **Prestar el servicio:** autenticación, gestión de estéticas, pacientes, turnos y tratamientos.  
- **Sincronización y offline:** guardar cambios en el dispositivo y sincronizarlos con Firebase cuando haya conexión.  
- **Seguridad y operación:** reglas de acceso en Firebase (por usuario y estética), y logs locales para soporte y diagnóstico.  
- **Cumplimiento legal:** responder a requerimientos válidos de autoridades cuando la ley lo exija.

No usamos los datos para publicidad ni para crear perfiles para fines de marketing.

---

## 5. Base legal y consentimiento

- **Ejecución del contrato / servicio:** el tratamiento de email, nombre, contraseña (y datos de pacientes/turnos/estéticas) es necesario para poder ofrecer la aplicación y las funciones descritas.  
- **Consentimiento:** al registrarse y usar la app, el usuario acepta esta política y el tratamiento descrito.  
- **Intereses legítimos:** logs locales y sincronización para estabilidad, seguridad y soporte técnico (sin compartir esos logs con terceros).

Si su ordenamiento aplica consentimiento explícito para datos sensibles (p. ej. salud), las observaciones o tratamientos relacionados con pacientes podrían requerir base adicional; en ese caso, el responsable lo indicará en la app o en una actualización de esta política.

---

## 6. Compartición con terceros

No vendemos ni alquilamos datos personales. Compartimos datos solo en estos casos:

| Tipo de dato | Con quién | Finalidad |
|--------------|------------|-----------|
| Datos de cuenta y de la app (usuarios, estéticas, pacientes, turnos) | **Google Firebase** (Auth + Realtime Database) | Autenticación y almacenamiento en la nube |
| Cualquier dato | **Autoridades competentes** | Cuando lo exija la ley o una orden judicial válida |

Firebase forma parte de Google LLC y está sujeto a la [Política de privacidad de Google](https://policies.google.com/privacy). Los datos se almacenan en los proyectos de Firebase que usa la aplicación (proyecto `steticapp-39adf`).

**Enlaces externos:** la app puede abrir enlaces a WhatsApp, Instagram o sitios web (p. ej. `wa.me`, `instagram.com`). Esas plataformas tienen sus propias políticas de privacidad; nosotros no controlamos los datos que el usuario comparta con ellas.

---

## 7. Almacenamiento y transferencias internacionales

- **Firebase:** Google puede procesar y almacenar datos en servidores fuera del país del usuario (p. ej. EE. UU. o regiones de Google Cloud). Google ofrece garantías (cláusulas contractuales tipo y, cuando aplica, certificaciones) según la normativa de protección de datos.  
- **Dispositivo:** los datos en SharedPreferences, cola offline y logs permanecen en el dispositivo del usuario y no se envían a nuestros propios servidores.  
- Si su legislación exige informar transferencias internacionales concretas, puede indicarse aquí la ubicación del proyecto Firebase (región configurada en Firebase Console).

---

## 8. Seguridad

- Usamos **Firebase Authentication** (email/contraseña) y **reglas de seguridad** en Realtime Database para limitar el acceso por usuario y estética.  
- La comunicación con Firebase se realiza por canales cifrados (HTTPS/TLS).  
- Los datos en el dispositivo se guardan en almacenamiento local de la app (SharedPreferences, directorios de la aplicación).  
- **Recomendación importante:** la app puede guardar temporalmente email y contraseña en el dispositivo para “recordar sesión”. Debe usar contraseñas fuertes y no compartir el dispositivo con terceros. El responsable del tratamiento debe valorar reducir o eliminar el almacenamiento local de contraseña (véase sección «Suposiciones»).

Ningún sistema es infalible; no podemos garantizar una seguridad absoluta frente a accesos no autorizados o fallos técnicos.

---

## 9. Retención y eliminación

- **Cuenta y datos en Firebase:** se conservan mientras la cuenta exista y el usuario use el servicio. Si solicita la **eliminación de la cuenta**, procederemos a borrar o anonimizar los datos personales que nos incumban en un plazo razonable (por ejemplo, 30 días), salvo retención legal.  
- **Datos en el dispositivo:** al desinstalar la app, SharedPreferences, cola offline y logs locales se eliminan con la aplicación. Los backups y logs en carpetas accesibles (p. ej. Documents/SteticappLogs en algunos dispositivos) pueden quedar en el dispositivo hasta que el usuario los borre manualmente.  
- **Firebase:** la eliminación de datos en Firebase (Auth y Realtime Database) debe hacerse desde la cuenta del desarrollador o mediante procesos que el responsable defina (p. ej. solicitud por email).  
- **Logs locales:** se rotan y se limita su número/tamaño en el código; no se envían a ningún servidor.

---

## 10. Derechos del usuario

Según la normativa aplicable (GDPR, CCPA, LGPD, etc.), usted puede tener derecho a:

- **Acceso:** saber qué datos tenemos sobre usted.  
- **Rectificación:** corregir datos inexactos o incompletos.  
- **Supresión:** pedir la eliminación de sus datos personales.  
- **Limitación:** en ciertos casos, limitar el tratamiento.  
- **Portabilidad:** recibir sus datos en formato estructurado de uso común.  
- **Oposición:** oponerse a determinados tratamientos.  
- **Retirar el consentimiento:** cuando el tratamiento se base en el consentimiento.

Para ejercer estos derechos, escriba a: **[email de privacidad/soporte — reemplazar]**.

Si considera que el tratamiento vulnera la normativa, puede presentar una reclamación ante la autoridad de protección de datos correspondiente.

---

## 11. Menores y «Designed for Families»

Steticapp **no** está dirigida a menores de 13 años ni está diseñada como app para familias («Designed for Families»). Es una herramienta profesional para negocios (estéticas y centros de belleza). No recopilamos intencionadamente datos de menores de 13 años. Si se detectara que se han obtenido datos de un menor sin el consentimiento parental exigido, se adoptarían medidas para eliminar esa información.

---

## 12. Contacto

Para preguntas sobre privacidad, ejercer derechos o notificar incidencias:

- **Email:** [email de privacidad/soporte — **reemplazar**]  
- **Asunto sugerido:** «Privacidad – Steticapp»

---

## 13. Cambios a esta política

Podemos actualizar esta política para reflejar cambios en la app, en la ley o en nuestras prácticas. Los cambios relevantes se comunicarán mediante una nueva versión en la app o en la URL donde se publique esta política, indicando la **última fecha de actualización** al inicio del documento. El uso continuado de la app tras la publicación de cambios implica la aceptación de la política actualizada, salvo cuando la ley exija un consentimiento explícito para determinados tratamientos.

---

## ⚠️ Suposiciones (confirmar por el responsable del proyecto)

Se han aplicado las siguientes suposiciones al redactar esta política. **Debe revisarlas y ajustar textos o datos antes de publicar:**

1. **Email de contacto:** No aparece un email de soporte/privacidad en el repositorio. Se ha usado el marcador `[email de privacidad/soporte — reemplazar]`. Debe sustituirse por un email real y estable.
2. **Nombre del desarrollador / responsable:** No hay razón social o nombre legal en el repo. Debe reemplazarse `[Nombre o razón social del desarrollador]` por el responsable del tratamiento de datos.
3. **Almacenamiento local de contraseña:** La app guarda email y contraseña en SharedPreferences para “recordar sesión”. Es un riesgo de privacidad y seguridad. Se recomienda valorar alternativas (p. ej. solo token/refresh, o no guardar contraseña en claro) y describir en la política la medida finalmente adoptada.
4. **Analytics y Crashlytics:** No están integrados en el código actual; la política no los menciona como activos. Si se activan más adelante, hay que actualizar esta política y, en su caso, el formulario de Data Safety en Play Console.
5. **Menores:** Se asume que la app no está dirigida a menores de 13 años y no participa en «Designed for Families». Si en el futuro se orientara a otros públicos, debe revisarse la sección 11.
6. **Región de Firebase:** No se ha verificado la región exacta del proyecto en Firebase Console. Si debe informarse expresamente (p. ej. UE/EE. UU.), conviene comprobarlo en la consola de Firebase.

---

*Documento generado en el marco de una auditoría de cumplimiento para Google Play (User Data Policy / Data Safety).*
