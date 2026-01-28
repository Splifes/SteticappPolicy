# Borrador — Seguridad de los datos (Play Console)

Este documento es un **borrador** para completar el formulario **«Seguridad de los datos»** de Google Play Console. Se basa en el inventario realizado sobre la app **Steticapp** (Firebase Auth, Realtime Database, SharedPreferences, logs locales, url_launcher).

**Cómo usarlo:** en Play Console → Tu app → Política → Seguridad de los datos, responde cada pregunta usando las opciones y textos sugeridos abajo. Ajusta según lo que confirmes (email de contacto, nombre del responsable, etc.).

---

## 1. ¿Recopila o comparte alguno de los tipos de datos de usuario requeridos?

**Respuesta sugerida:** **Sí.**

---

## 2. Tipos de datos que recopila o comparte

Completa para cada tipo que aplique. En Steticapp aparecen los siguientes según el inventario:

### 2.1 Información personal

| Tipo de dato (Play Console) | ¿Se recopila? | ¿Se comparte? | ¿Obligatorio u opcional? | Finalidad (resumen) |
|-----------------------------|---------------|---------------|--------------------------|----------------------|
| **Nombre** | Sí | Sí (Firebase/Google) | Obligatorio para cuenta y perfil | Identificación del usuario y de la estética |
| **Dirección de email** | Sí | Sí (Firebase/Google) | Obligatorio | Autenticación, cuenta, recuperación de sesión |
| **Identificador de usuario** (UID Firebase) | Sí | Sí (Firebase/Google) | Automático | Vincular datos a la cuenta |

### 2.2 Información financiera

| Tipo de dato | ¿Se recopila? | ¿Se comparte? | Notas |
|--------------|---------------|----------------|-------|
| **Información de pago** (tarjetas, cuentas bancarias) | No | No | La app no procesa pagos directamente |
| **Historial de compras** | No | No | — |

*(Si en el futuro integras Stripe/RevenueCat u otro proveedor de pagos, habrá que añadir aquí los datos que recopilen.)*

### 2.3 Ubicación

| Tipo de dato | ¿Se recopila? | ¿Se comparte? | Notas |
|--------------|---------------|----------------|-------|
| **Ubicación aproximada** | No | No | No hay permisos de ubicación en AndroidManifest |
| **Ubicación precisa** | No | No | — |

### 2.4 Actividad en la app

| Tipo de dato | ¿Se recopila? | ¿Se comparte? | Notas |
|--------------|---------------|----------------|-------|
| **Historial de búsquedas** | No | No | No hay analytics ni búsquedas enviadas a servidor |
| **Interacciones en la app** | No (con terceros) | No | Los logs de acciones son solo locales |
| **Otros datos de uso** | No (con terceros) | No | No hay Firebase Analytics/Crashlytics en uso actual |

*(Si añades Firebase Analytics u otro analytics, habrá que marcar “Sí” y describir finalidad y base legal.)*

### 2.5 Archivos y documentos

| Tipo de dato | ¿Se recopila? | ¿Se comparte? | Notas |
|--------------|---------------|----------------|-------|
| **Fotos o vídeos** | No | No | No hay subida de fotos en el código revisado |
| **Archivos y documentos** | No | No | — |

### 2.6 Datos sensibles (según Google Play)

| Tipo de dato | ¿Se recopila? | ¿Se comparte? | Notas |
|--------------|---------------|----------------|-------|
| **Información de salud** | Sí (parcial) | Sí (Firebase) | Observaciones de pacientes, tratamientos sugeridos, datos de turnos (contexto estético/ belleza) |
| **Información de contacto** (teléfono de pacientes) | Sí | Sí (Firebase) | Gestión de fichas de pacientes y enlaces a WhatsApp |
| **Otras categorías sensibles** | Revisar | — | La contraseña guardada localmente es un dato sensible; no se “comparte” con terceros pero sí se almacena en el dispositivo |

**Resumen para “Datos sensibles” en Play Console:**

- **Información de salud:** Marcar **Sí** si en tu jurisdicción las observaciones/tratamientos de la app se consideran “información de salud”. Describir: “Observaciones de pacientes, tratamientos sugeridos y datos de turnos en contexto de servicios estéticos/centros de belleza. Se usan para la gestión de la agenda y fichas de pacientes. Se almacenan en Firebase Realtime Database.”
- **Información de contacto (teléfonos de pacientes):** Marcar **Sí**. Describir: “Números de teléfono de pacientes introducidos por el usuario para gestionar fichas y opcionalmente contactar por WhatsApp. Se almacenan en Firebase Realtime Database.”

---

## 3. ¿Los datos se comparten con terceros?

**Respuesta sugerida:** **Sí.**

**Terceros a declarar:**

| Proveedor | Datos que recibe | Finalidad |
|-----------|------------------|-----------|
| **Google (Firebase)** | Email, nombre, UID, datos de usuarios/estéticas/pacientes/turnos/tratamientos | Autenticación (Firebase Auth) y almacenamiento (Realtime Database) |

**¿Los datos se comparten para publicidad?** **No.**

**¿Se encriptan en tránsito?** **Sí** (HTTPS/TLS a servicios Firebase).

---

## 4. ¿Los usuarios pueden solicitar que se eliminen sus datos?

**Respuesta sugerida:** **Sí.**

**Texto sugerido para la sección correspondiente:**

> “Los usuarios pueden solicitar la eliminación de sus datos personales y de su cuenta escribiendo a [EMAIL_DE_PRIVACIDAD]. Procederemos a eliminar o anonimizar los datos que nos incumban en un plazo razonable (por ejemplo, 30 días), salvo retención legal. Al desinstalar la app, los datos almacenados solo en el dispositivo (incluidos los de sesión guardada) se eliminan con la aplicación.”

*(Sustituir [EMAIL_DE_PRIVACIDAD] por el email real.)*

---

## 5. Lista de comprobación rápida (Data Safety)

Antes de publicar en Play Console, confirma:

- [ ] **Email de privacidad/soporte** definido y visible en la ficha de la app y en la política de privacidad.
- [ ] **URL de la Política de Privacidad** pública y accesible (la misma que pondrás en Play Console).
- [ ] **“¿Recopila o comparte datos?”** respondido en coherencia con este borrador.
- [ ] **Datos sensibles:** Decidido si declaras “información de salud” según tu jurisdicción y tipo de datos (observaciones, tratamientos, etc.).
- [ ] **Terceros:** Solo Firebase (Auth + Realtime Database) declarados; si añades Analytics, Crashlytics, FCM o proveedores de pago, actualizar formulario y política.
- [ ] **Eliminación de datos:** Proceso claro (email, plazos) y descrito en la política y en la sección de Data Safety.
- [ ] **Menores:** Confirmado que la app no está dirigida a menores de 13 años y no está en “Designed for Families”.

---

## 6. Inventario de datos (resumen para auditoría)

| Dato | Fuente | Finalidad | Almacenamiento | ¿Compartido? | Retención |
|------|--------|-----------|----------------|--------------|-----------|
| Email | Usuario | Cuenta, auth | Dispositivo, Firebase Auth, RTDB | Firebase/Google | Hasta eliminación de cuenta / desinstalación |
| Contraseña | Usuario | Sesión local “recordar” | Solo dispositivo (SharedPreferences) | No | Hasta cierre de sesión o desinstalación |
| Nombre (usuario) | Usuario | Perfil | Dispositivo, Firebase RTDB | Firebase/Google | Igual que email |
| UID (Firebase) | Sistema | Identificación | Dispositivo, Firebase | Firebase/Google | Igual que email |
| Pacientes: nombre, apellido, teléfono, email, fecha nac., género, observaciones, redes, tratamientos sugeridos | Usuario (introducidos en la app) | Fichas y agenda | Firebase RTDB, caché/offline en dispositivo | Firebase/Google | Mientras exista la estética / eliminación bajo solicitud |
| Turnos: paciente, fecha/hora, operador, pago, observaciones, etc. | Usuario / sistema | Agenda y estadísticas | Firebase RTDB, cola offline, logs locales | Firebase/Google (solo datos en RTDB) | Igual que pacientes |
| Estéticas: nombre, tipo, miembros, códigos invitación | Usuario | Multi‑estética y equipos | Firebase RTDB, dispositivo | Firebase/Google | Igual que usuarios |
| Cola offline (acciones pendientes de sync) | Sistema | Sincronización | Dispositivo (SharedPreferences + backups) | No | Hasta sincronizar o desinstalar |
| Logs de acciones (tipo, ID, nombres, usuario) | Sistema | Diagnóstico/soporte | Solo dispositivo | No | Rotación por tamaño/cantidad; no se envían a servidor |

---

*Borrador generado en el marco de una auditoría de cumplimiento para Google Play (User Data Policy / Data Safety). Debe ser revisado por el responsable del proyecto antes de enviar el formulario en Play Console.*
