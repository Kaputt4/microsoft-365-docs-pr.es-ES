---
title: Detectar y corregir las reglas de Outlook y los ataques de inserciones de formularios personalizados.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Obtenga información sobre cómo reconocer y corregir las reglas de Outlook y los ataques de inserciones de formularios personalizados en Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286398"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Detectar y corregir reglas de Outlook y ataques de inserciones de formularios personalizados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Resumen** Obtenga información sobre cómo reconocer y corregir las reglas de Outlook y los ataques de inserciones de formularios personalizados en Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>¿Qué son las reglas de Outlook y el ataque de inserción de formularios personalizados?

Después de que un atacante ha infringido una cuenta en su arrendamiento y entra, va a intentar establecer una forma de permanecer o una forma de volver a entrar después de que se descubran y quiten. Esto se denomina establecimiento de un mecanismo de persistencia. Dos formas de hacerlo son mediante la vulnerabilidad de las reglas de Outlook o mediante la inyección de formularios personalizados en Outlook.
En ambos casos, la regla o el formulario se sincroniza desde el servicio en la nube hasta el cliente de escritorio, por lo que un formato completo y la nueva instalación del software cliente no eliminan el mecanismo de inserción. Esto se debe a que cuando el software cliente de Outlook se vuelve a conectar al buzón en la nube, volverá a descargar las reglas y los formularios de la nube. Una vez que las reglas y los formularios están en su lugar, el atacante las usa para ejecutar código remoto o personalizado, normalmente para instalar malware en el equipo local. A continuación, el malware vuelve a robar las credenciales o realiza otra actividad ilegal.
La buena noticia aquí es que si mantiene sus clientes con revisiones a la versión más reciente, no es vulnerable a la amenaza, ya que los valores predeterminados actuales del cliente de Outlook bloquean ambos mecanismos.

Los ataques suelen seguir estos patrones:

**La vulnerabilidad de seguridad de reglas:**

1. El atacante roba el nombre de usuario y la contraseña de uno de los usuarios.

2. A continuación, el atacante inicia sesión en ese buzón de Exchange para los usuarios. El buzón puede estar en Exchange Online o en Exchange local.

3. A continuación, el atacante crea una regla de reenvío en el buzón que se desencadena cuando el buzón recibe un correo electrónico que coincide con los criterios de la regla. Los criterios de regla y el contenido del correo electrónico desencadenador se adaptan entre sí.

4. El atacante envía el correo electrónico desencadenador al usuario que usa su buzón normalmente.

5. Cuando se recibe el correo electrónico, se desencadena la regla. La acción de la regla suele ser iniciar una aplicación en un servidor remoto (WebDAV).

6. Por lo general, la aplicación instala malware, como [PowerShell Enerbado,](https://www.powershellempire.com/)localmente en el equipo del usuario.

7. El malware permite al atacante volver a robar el nombre de usuario y la contraseña del usuario u otras credenciales del equipo local y realizar otras actividades malintencionadas.

**La vulnerabilidad de seguridad de formularios:**

1. El atacante roba el nombre de usuario y la contraseña de uno de los usuarios.

2. A continuación, el atacante inicia sesión en ese buzón de Exchange para los usuarios. El buzón puede estar en Exchange Online o en Exchange local.

3. A continuación, el atacante crea una plantilla de formulario de correo personalizada y la inserta en el buzón del usuario. El formulario personalizado se desencadena cuando el buzón recibe un correo electrónico que requiere que el buzón cargue el formulario personalizado. El formulario personalizado y el formato del correo electrónico se personalizan entre sí.
4. El atacante envía el correo electrónico desencadenador al usuario, que usa su buzón normalmente.

5. Cuando se recibe el correo electrónico, se carga el formulario. El formulario inicia una aplicación en un servidor remoto (WebDAV).

6. Por lo general, la aplicación instala malware, como [PowerShell Enerbado,](https://www.powershellempire.com/)localmente en el equipo del usuario.

7. El malware permite al atacante volver a robar el nombre de usuario y la contraseña del usuario u otras credenciales del equipo local y realizar otras actividades malintencionadas.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>What a Rules and Custom Forms Injection attack might look like Office 365?

Es poco probable que los usuarios noten estos mecanismos de persistencia y, en algunos casos, incluso pueden ser invisibles para ellos. En este artículo se explica cómo buscar cualquiera de los siete signos (Indicadores de peligro) que se enumeran a continuación. Si encuentra alguno de estos, debe realizar los pasos de corrección.

- Indicadores de las reglas en peligro:

  - La acción de regla es iniciar una aplicación.

  - La regla hace referencia a una dirección URL, ZIP o EXE.

  - En el equipo local, busque nuevos inicios de proceso que se originan en el PID de Outlook.

- Los indicadores de los formularios personalizados están en peligro:

  - Formulario personalizado presente guardado como su propia clase de mensaje.

  - La clase de mensaje contiene código ejecutable.

  - Normalmente se almacena en carpetas de la Bandeja de entrada o biblioteca de formularios personales.

  - El formulario se denomina IPM. Nota. [nombre personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Pasos para encontrar signos de este ataque y confirmarlo

Puedes usar cualquiera de estos dos métodos para confirmar el ataque:

- Examine manualmente las reglas y los formularios de cada buzón mediante el cliente de Outlook. Este método es minucioso, pero solo puede comprobar el usuario del buzón a la vez, lo que puede llevar mucho tiempo si tiene muchos usuarios que comprobar. También puede provocar una infracción del equipo desde el que se está ejecutando la comprobación.

- Use el [ scriptGet-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell para volcar automáticamente todas las reglas de reenvío de correo y los formularios personalizados para todos los usuarios de su arrendamiento. Este es el método más rápido y seguro con la menor cantidad de sobrecarga.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmar el ataque de reglas mediante el cliente de Outlook

1. Abra el cliente de Outlook de los usuarios como el usuario. Es posible que el usuario necesite su ayuda para examinar las reglas de su buzón.

2. Consulte Administrar [mensajes de correo electrónico mediante el artículo de reglas](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) para obtener información sobre los procedimientos para abrir la interfaz de reglas en Outlook.

3. Busque reglas que el usuario no ha creado o reglas o reglas inesperadas con nombres sospechosos.

4. Busque en la descripción de la regla acciones de regla que se inician y se aplica o hacen referencia a un archivo . EXE, . Archivo ZIP o para iniciar una dirección URL.

5. Busque los procesos nuevos que empiecen a usar el identificador de proceso de Outlook. Consulte Buscar [el id. de proceso.](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Pasos para confirmar el ataque de formularios con el cliente de Outlook

1. Abra el cliente de Outlook del usuario como el usuario.

2. Siga los pasos que se indican en la [pestaña Programador](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) para la versión de usuarios de Outlook.

3. Abra la pestaña de desarrollador visible en Outlook y haga clic **en diseñar un formulario.**

4. Seleccione la **Bandeja de entrada** de la lista Buscar **en.** Busque los formularios personalizados. Los formularios personalizados son lo suficientemente raros como para que, si tiene algún formulario personalizado, merece la pena tener un aspecto más profundo.

5. Investigue los formularios personalizados, especialmente los marcados como ocultos.

6. Abra los formularios personalizados y, en **el** grupo **formulario,** haga clic en Ver código para ver qué se ejecuta cuando se carga el formulario.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Pasos para confirmar el ataque de reglas y formularios con PowerShell

La forma más sencilla de comprobar un ataque [](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) de reglas o formularios personalizados es ejecutarGet-AllTenantRulesAndForms.ps1script de PowerShell. Este script se conecta a todos los buzones del espacio empresarial y volca todas las reglas y formularios en dos archivos .csv.

#### <a name="pre-requisites"></a>Requisitos previos

Deberá tener derechos de administrador global para ejecutar el script porque el script se conecta a todos los buzones del arrendamiento para leer las reglas y los formularios.

1. Inicia sesión en el equipo desde el que ejecutarás el script con derechos de administrador local.

2. Descargue o copie el script Get-AllTenantRulesAndForms.ps1 de GitHub en una carpeta desde la que lo ejecutará. El script creará dos archivos con marca de fecha en esta carpeta, MailboxFormsExport-yyyy-mm-dd.csv y MailboxRulesExport-yyyy-mm-dd.csv.

3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.

4. Ejecute esta línea de comandos de PowerShell de la siguiente `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretar el resultado

- **MailboxRulesExport-*yyyy-mm-dd*.csv:** examine las reglas (una por fila) en busca de condiciones de acción que incluyan aplicaciones o ejecutables:

  - **ActionType (columna A):** si ve el valor "ID_ACTION_CUSTOM", es probable que la regla sea malintencionada.

  - **IsPotentiallyMalicious (columna D):** si este valor es "TRUE", es probable que la regla sea malintencionada.

  - **ActionCommand (columna G):** si se muestra una aplicación o un archivo con una extensión .exe, .zip o una entrada que hace referencia a una dirección URL, que no está ahí, es probable que la regla sea malintencionada.

- **MailboxFormsExport-*yyyy-mm-dd*.csv:** En general, el uso de formularios personalizados es muy raro. Si encuentra alguno en este libro, abra el buzón del usuario y examine el propio formulario. Si su organización no la ha puesto allí de forma intencionada, es probable que sea malintencionada.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Cómo detener y corregir el ataque de formularios y reglas de Outlook

Si encuentra pruebas de cualquiera de estos ataques, la corrección es sencilla, simplemente elimine la regla o el formulario del buzón. Puede hacerlo con el cliente de Outlook o con PowerShell remoto para quitar reglas.

### <a name="using-outlook"></a>Uso de Outlook

1. Identifique todos los dispositivos que el usuario ha usado con Outlook. Todos ellos tendrán que limpiarse de posible malware. No permita que el usuario inicie sesión y use el correo electrónico hasta que se limpien todos los dispositivos.

2. Sigue los pasos de [Eliminar una regla](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) para cada dispositivo.

3. Si no estás seguro de la presencia de otro malware, puedes formatear y volver a instalar todo el software en el dispositivo. Para dispositivos móviles, puedes seguir los pasos de los fabricantes para restablecer el dispositivo a la imagen de fábrica.

4. Instale las versiones más actualizadas de Outlook. Recuerde que la versión actual de Outlook bloquea ambos tipos de este ataque de forma predeterminada.

5. Una vez que se hayan quitado todas las copias sin conexión del buzón, restablezca la contraseña del usuario (use una de alta calidad) y siga los pasos descritos en la configuración de la autenticación [multifactor](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) para los usuarios si aún no se ha habilitado MFA. Esto garantiza que las credenciales del usuario no se exponen a través de otros medios (como suplantación de identidad o volver a usar la contraseña).

### <a name="using-powershell"></a>Mediante PowerShell

Hay dos cmdlets de PowerShell remotos que puede usar para quitar o deshabilitar reglas peligrosas. Solo tiene que seguir los pasos.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Pasos para los buzones que están en un servidor Exchange

1. Conéctese al servidor Exchange con PowerShell remoto. Siga los pasos descritos en [Conectarse a servidores de Exchange con PowerShell remoto.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Si desea quitar completamente una sola regla, varias reglas o todas las reglas de un buzón, use el cmdlet [Remove-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Si desea conservar la regla y su contenido para una investigación posterior, use el cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Pasos para buzones en Exchange Online

1. Siga los pasos descritos [en Conectarse a Exchange Online con PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Si desea quitar completamente una sola regla, varias reglas o todas las reglas de un buzón, use el cmdlet [Remove-Inbox Rule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Si desea conservar la regla y su contenido para una investigación posterior, use el cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Cómo minimizar ataques futuros

### <a name="first-protect-your-accounts"></a>En primer lugar: proteger las cuentas

Las vulnerabilidades de seguridad de reglas y formularios solo las usa un atacante después de haber robado o infringido una de las cuentas de usuario. Por lo tanto, el primer paso para evitar el uso de estas vulnerabilidades de seguridad en la organización es proteger de forma agresiva las cuentas de usuario. Algunas de las formas más comunes de que se infringen las cuentas son a través de ataques de suplantación de identidad (phishing) o [de protección contra contraseñas.](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)

La mejor manera de proteger las cuentas de usuario, y especialmente las cuentas de administrador, es configurar la autenticación [multifactor para los usuarios.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) También debe:

- Supervise cómo se accede a las cuentas [de usuario y cómo se usan.](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Es posible que no evite la infracción inicial, pero acortará la duración y el impacto de la infracción detectándose antes. Puede usar estas directivas de [Office 365 Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para supervisar las cuentas y alertar sobre actividad inusual:

  - **Varios** intentos de inicio de sesión fallidos: esta directiva perfila su entorno y desencadena alertas cuando los usuarios realizan varias actividades de inicio de sesión con errores en una sola sesión con respecto a la línea base aprendida, lo que podría indicar un intento de infracción.

  - **Viajes imposibles:** esta directiva perfila su entorno y desencadena alertas cuando se detectan actividades del mismo usuario en diferentes ubicaciones en un período de tiempo que es más corto que el tiempo de viaje esperado entre las dos ubicaciones. Esto podría indicar que un usuario diferente está usando las mismas credenciales. La detección de este comportamiento anómalo requiere un período de aprendizaje inicial de siete días durante el cual se aprende el patrón de actividad de un nuevo usuario.

  - Actividad suplantada inusual **(por usuario):** esta directiva perfila el entorno y desencadena alertas cuando los usuarios realizan varias actividades suplantadas en una sola sesión con respecto a la línea base aprendida, lo que podría indicar un intento de infracción.

- Aproveche una herramienta como [Puntuación de seguridad de Office 365](https://securescore.office.com/) para administrar los comportamientos y configuraciones de seguridad de la cuenta.

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: Mantener los clientes de Outlook al día

Las versiones actualizadas y con revisión de Outlook 2013 y 2016 deshabilitan la acción de formulario o regla "Iniciar aplicación" de forma predeterminada. Esto garantizará que, incluso si un atacante infringe la cuenta, las acciones de regla y formulario se bloquearán. Puede instalar las actualizaciones y revisiones de seguridad más recientes siguiendo los pasos descritos [en Instalar actualizaciones de Office.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Estas son las versiones de revisión para sus clientes de Outlook 2013 y 2016:

- **Outlook 2016**: 16.0.4534.1001 o posterior.

- **Outlook 2013**: 15.0.4937.1000 o posterior.

Para obtener más información sobre las revisiones de seguridad individuales, vea:

- [Revisión de seguridad de Outlook 2016](https://support.microsoft.com/help/3191883)

- [Revisión de seguridad de Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Tercero: supervisar los clientes de Outlook

Ten en cuenta que incluso con las revisiones y actualizaciones instaladas, es posible que un atacante cambie la configuración del equipo local para volver a habilitar el comportamiento "Iniciar aplicación". Puedes usar la [Administración avanzada de directivas de grupo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) para supervisar y aplicar directivas de equipo local en los clientes.

Puede ver si "Iniciar aplicación" se ha habilitado de nuevo a través de una invalidación en el Registro mediante la información de Cómo ver el registro del sistema mediante versiones de [64](https://support.microsoft.com/help/305097)bits de Windows . Compruebe estas subclaves:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013:**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Busque la clave EnableUnsafeClientMailRules. Si está ahí y se establece en 1, se ha invalidado la revisión de seguridad de Outlook y el equipo es vulnerable al ataque de formulario o reglas. Si el valor es 0, se deshabilita la acción "Iniciar aplicación". Si la versión actualizada y con revisión de Outlook está instalada y esta clave del Registro no está presente, entonces un sistema no es vulnerable a estos ataques.

Los clientes con instalaciones de Exchange locales deben considerar el bloqueo de versiones anteriores de Outlook que no tienen revisiones disponibles. Puede encontrar detalles sobre este proceso en el artículo [Configurar el bloqueo de cliente de Outlook.](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteger Microsoft 365 como un profesional de la ciberseguridad

Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios. Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.

- Tareas a realizar en los primeros 30 días. Estas tienen un efecto inmediato y de bajo impacto para los usuarios.

- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.

- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también:

- [Las reglas malintencionadas](https://silentbreaksecurity.com/malicious-outlook-rules/) de SilentBreak Security Post sobre el vector de reglas proporcionan una revisión detallada de cómo se aplican las reglas de Outlook.

- MAPI sobre HTTP y [Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) en el blog sensepost sobre Mailrule Pwnage analiza una herramienta denominada Ruler que le permite aprovechar los buzones a través de reglas de Outlook.

- [Formularios y shells de Outlook](https://sensepost.com/blog/2017/outlook-forms-and-shells/) en el blog sensepost sobre el vector de amenaza de formularios.

- [Código base de regla](https://github.com/sensepost/ruler)

- [Indicadores de regla de peligro](https://github.com/sensepost/notruler/blob/master/iocs.md)
