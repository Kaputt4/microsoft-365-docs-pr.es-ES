---
title: Detecte y corrija las reglas de Outlook y los ataques por inyección de formularios personalizados.
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
ms.localizationpriority: medium
search.appverid:
- MET150
description: Aprenda a reconocer y corregir las reglas de Outlook y los ataques de inyecciones de formularios personalizados en Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 10cbb57018cb0e7c30282ca2c89b6a8dab812e24
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131116"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Detección y corrección de reglas de Outlook y ataques por inyección de formularios personalizados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Resumen** Obtenga información sobre cómo reconocer y corregir las reglas de Outlook y los ataques de inyecciones de formularios personalizados en Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>¿Cuál es el ataque por inyección de reglas de Outlook y formularios personalizados?

Después de que un atacante obtenga acceso a su organización, intentará establecer un punto de apoyo para permanecer en o volver a entrar después de que se haya detectado. Esta actividad se denomina *establecimiento de un mecanismo de persistencia*. Hay dos maneras en que un atacante puede usar Outlook para establecer un mecanismo de persistencia:

- Mediante la explotación de Outlook reglas.
- Insertando formularios personalizados en Outlook.

Volver a instalar Outlook o incluso dar a la persona afectada un nuevo equipo no le ayudará. Cuando la nueva instalación de Outlook se conecta al buzón de correo, todas las reglas y formularios se sincronizan desde la nube. Las reglas o formularios se suelen diseñar para ejecutar código remoto e instalar malware en el equipo local. El malware roba credenciales o realiza otra actividad ilícita.

La buena noticia es que, si mantiene los clientes de Outlook revisados a la versión más reciente, no es vulnerable a la amenaza, ya que los valores predeterminados actuales Outlook cliente bloquean ambos mecanismos.

Los ataques suelen seguir estos patrones:

**Vulnerabilidad de seguridad de reglas**:

1. El atacante roba las credenciales de un usuario.

2. El atacante inicia sesión en el buzón de Exchange de ese usuario (Exchange Online o Exchange local).

3. El atacante crea una regla de bandeja de entrada de reenvío en el buzón de correo. La regla de reenvío se desencadena cuando el buzón recibe un mensaje específico del atacante que coincide con las condiciones de la regla. Las condiciones de regla y el formato de mensaje se adaptan entre sí.

4. El atacante envía el correo electrónico del desencadenador al buzón en peligro, que sigue siendo utilizado con normalidad por el usuario desprevenido.

5. Cuando el buzón recibe un mensaje que coincide con las condiciones de regla, se aplica la acción de la regla. Normalmente, la acción de regla consiste en iniciar una aplicación en un servidor remoto (WebDAV).

6. Normalmente, la aplicación instala malware en el equipo del usuario (por ejemplo, [PowerShell Empire](https://www.powershellempire.com/)).

7. El malware permite al atacante robar (o robar de nuevo) el nombre de usuario y la contraseña del usuario u otras credenciales de la máquina local y realizar otras actividades malintencionadas.

**Vulnerabilidad de seguridad de formularios**:

1. El atacante roba las credenciales de un usuario.

2. El atacante inicia sesión en el buzón de Exchange de ese usuario (Exchange Online o Exchange local).

3. El atacante inserta una plantilla de formulario de correo personalizado en el buzón del usuario. El formulario personalizado se desencadena cuando el buzón recibe un mensaje específico del atacante que requiere que el buzón cargue el formulario personalizado. El formulario personalizado y el formato de mensaje se personalizan entre sí.

4. El atacante envía el correo electrónico del desencadenador al buzón en peligro, que sigue siendo utilizado con normalidad por el usuario desprevenido.

5. Cuando el buzón recibe el mensaje, el buzón carga el formulario necesario. El formulario inicia una aplicación en un servidor remoto (WebDAV).

6. Normalmente, la aplicación instala malware en el equipo del usuario (por ejemplo, [PowerShell Empire](https://www.powershellempire.com/)).

7. El malware permite al atacante robar (o robar de nuevo) el nombre de usuario y la contraseña del usuario u otras credenciales de la máquina local y realizar otras actividades malintencionadas.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>¿Qué aspecto podría tener un ataque por inyección de reglas y formularios personalizados Office 365?

Es poco probable que los usuarios noten estos mecanismos de persistencia y, en algunos casos, incluso pueden ser invisibles para ellos. En este artículo se explica cómo buscar cualquiera de los siete signos (Indicadores de compromiso) que se enumeran a continuación. Si encuentra alguno de estos, debe realizar los pasos de corrección.

- **Indicadores del compromiso de reglas**:
  - La acción de regla es iniciar una aplicación.
  - Regla Hace referencia a una dirección EXE, ZIP o URL.
  - En el equipo local, busque nuevos inicios de proceso que se originen en el PID de Outlook.

- **Los indicadores de los formularios personalizados están en peligro**:
  - Formularios personalizados presentes guardados como su propia clase de mensaje.
  - La clase message contiene código ejecutable.
  - Normalmente, los formularios malintencionados se almacenan en las carpetas Biblioteca de formularios personales o Bandeja de entrada.
  - El formulario se denomina IPM. Nota. [nombre personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Pasos para encontrar signos de este ataque y confirmarlo

Puede usar cualquiera de los métodos siguientes para confirmar el ataque:

- Examine manualmente las reglas y los formularios de cada buzón mediante el cliente de Outlook. Este método es exhaustivo, pero solo puede comprobar un buzón a la vez. Este método puede llevar mucho tiempo si tiene muchos usuarios que comprobar y también puede infectar el equipo que está usando.

- Use el script [ de PowerShellGet-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) para volcar automáticamente todas las reglas de reenvío de correo y los formularios personalizados para todos los usuarios del inquilino. Este es el método más rápido y seguro con la menor cantidad de sobrecarga.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmación del ataque de reglas mediante el cliente de Outlook

1. Abra los usuarios Outlook cliente como usuario. Es posible que el usuario necesite ayuda para examinar las reglas de su buzón de correo.

2. Consulte el artículo [Administración de mensajes de correo electrónico mediante reglas](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) para ver los procedimientos para abrir la interfaz de reglas en Outlook.

3. Busque las reglas que el usuario no creó o las reglas o reglas inesperadas con nombres sospechosos.

4. Busque en la descripción de la regla las acciones de regla que se inicien y a la aplicación o que hagan referencia a un .EXE, .ZIP archivo o que inicien una dirección URL.

5. Busque los nuevos procesos que empiecen a usar el identificador de proceso de Outlook. Consulte [Buscar el identificador de proceso](/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Pasos para confirmar el ataque de Forms mediante el cliente de Outlook

1. Abra el usuario Outlook cliente como usuario.

2. Siga los pasos descritos en [la pestaña Mostrar el programador](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) de la versión del usuario de Outlook.

3. Abra la pestaña ahora visible para desarrolladores en Outlook y haga clic en **Diseñar un formulario**.

4. Seleccione la **Bandeja de entrada en** la lista **Buscar en** . Busque los formularios personalizados. Los formularios personalizados son lo suficientemente raros como para que, si tiene formularios personalizados, valga la pena un vistazo más profundo.

5. Investigue los formularios personalizados, especialmente los marcados como ocultos.

6. Abra los formularios personalizados y, en el grupo **Formulario** , haga clic en **Ver código** para ver qué se ejecuta cuando se carga el formulario.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Pasos para confirmar el ataque de reglas y formularios mediante PowerShell

La manera más sencilla de comprobar un ataque de reglas o formularios personalizados es ejecutar el [ script de ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShellGet-AllTenantRulesAndForms.ps1. Este script se conecta a cada buzón del inquilino y volcado todas las reglas y formularios en dos archivos .csv.

#### <a name="pre-requisites"></a>Requisitos previos

Tendrá que tener derechos de administrador global para ejecutar el script porque el script se conecta a todos los buzones del inquilino para leer las reglas y los formularios.

1. Inicie sesión en la máquina desde la que ejecutará el script con derechos de administrador local.

2. Descargue o copie el script de Get-AllTenantRulesAndForms.ps1 de GitHub en una carpeta desde la que lo ejecutará. El script creará dos archivos con marca de fecha en esta carpeta, MailboxFormsExport-yyyy-mm-dd.csv y MailboxRulesExport-yyyy-mm-dd.csv.

3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.

4. Ejecute esta línea de comandos de PowerShell de la siguiente manera: `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretación de la salida

- ***MailboxRulesExport-aaaa-mm-dd*.csv**: Examine las reglas (una por fila) para ver las condiciones de acción que incluyen aplicaciones o ejecutables:

  - **ActionType (columna A):** si ve el valor "ID_ACTION_CUSTOM", es probable que la regla sea malintencionada.

  - **IsPotentiallyMalicious (columna D):** si este valor es "TRUE", es probable que la regla sea malintencionada.

  - **ActionCommand (columna G):** si esta columna enumera una aplicación o cualquier archivo con extensiones .exe o .zip, o una entrada desconocida que hace referencia a una dirección URL, es probable que la regla sea malintencionada.

- ***MailboxFormsExport-aaaa-mm-dd*.csv**: En general, el uso de formularios personalizados es poco frecuente. Si encuentra alguno en este libro, abra el buzón de ese usuario y examine el propio formulario. Si su organización no la puso allí intencionadamente, es probable que sea malintencionada.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Cómo detener y corregir el ataque de reglas y formularios de Outlook

Si encuentra alguna evidencia de cualquiera de estos ataques, la corrección es sencilla, simplemente elimine la regla o el formulario del buzón. Puede hacerlo con el cliente Outlook o con PowerShell remoto para quitar reglas.

### <a name="using-outlook"></a>Uso de Outlook

1. Identifique todos los dispositivos que el usuario ha usado con Outlook. Todos ellos tendrán que ser limpiados de posibles malware. No permita que el usuario inicie sesión y use el correo electrónico hasta que se limpien todos los dispositivos.

2. Siga los pasos descritos en [Eliminar una regla](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) para cada dispositivo.

3. Si no está seguro de la presencia de otro malware, puede formatear y reinstalar todo el software en el dispositivo. En el caso de los dispositivos móviles, puede seguir los pasos de los fabricantes para restablecer el dispositivo a la imagen de fábrica.

4. Instale las versiones más actualizadas de Outlook. Recuerde que la versión actual de Outlook bloquea ambos tipos de este ataque de forma predeterminada.

5. Una vez que se hayan quitado todas las copias sin conexión del buzón de correo, restablezca la contraseña del usuario (use una de alta calidad) y siga los pasos descritos en Configuración de la [autenticación multifactor para los usuarios](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) si MFA aún no se ha habilitado. Esto garantiza que las credenciales del usuario no se exponen a través de otros medios (como suplantación de identidad (phishing) o reutilización de contraseñas.

### <a name="using-powershell"></a>Con PowerShell

Hay dos cmdlets remotos de PowerShell que puede usar para quitar o deshabilitar reglas peligrosas. Siga los pasos.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Pasos para los buzones de correo que están en un servidor Exchange

1. Conectar al servidor de Exchange mediante PowerShell remoto. Siga los pasos de [Conectar para Exchange servidores mediante PowerShell remoto](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).

2. Si desea quitar completamente una sola regla, varias reglas o todas las reglas de un buzón, use el cmdlet [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) .

3. Si desea conservar la regla y su contenido para una investigación posterior, use el cmdlet [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) .

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Pasos para buzones de Exchange Online

1. Siga los pasos de [Conectar para Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Si desea quitar completamente una sola regla, varias reglas o todas las reglas de un buzón, use el cmdlet [Remove-Inbox Rule](/powershell/module/exchange/Remove-InboxRule) .

3. Si desea conservar la regla y su contenido para una investigación posterior, use el cmdlet [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) .

## <a name="how-to-minimize-future-attacks"></a>Cómo minimizar ataques futuros

### <a name="first-protect-your-accounts"></a>En primer lugar: proteger sus cuentas

Las vulnerabilidades de seguridad de reglas y formularios solo las usa un atacante después de haber robado o infringido una de las cuentas de usuario. Por lo tanto, el primer paso para evitar el uso de estas vulnerabilidades de seguridad en su organización es proteger de forma agresiva las cuentas de usuario. Algunas de las formas más comunes de vulnerar las cuentas son a través de ataques de suplantación de identidad (phishing) o [de difusión de contraseñas](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/).

La mejor manera de proteger las cuentas de usuario, y especialmente las cuentas de administrador, es [configurar la autenticación multifactor para los usuarios](../../admin/security-and-compliance/set-up-multi-factor-authentication.md). También debe:

- Supervise cómo se [accede y se usa a](/azure/active-directory/active-directory-view-access-usage-reports) las cuentas de usuario. Es posible que no impida la vulneración inicial, pero acortará la duración y el impacto de la infracción detectándola antes. Puede usar estas [directivas de Office 365 Cloud App Security](/cloud-app-security/what-is-cloud-app-security) para supervisar las cuentas y alertar sobre la actividad inusual:

  - **Varios intentos de inicio de sesión erróneos**: esta directiva genera perfiles de su entorno y desencadena alertas cuando los usuarios realizan varias actividades de inicio de sesión con errores en una sola sesión con respecto a la línea base aprendida, lo que podría indicar un intento de infracción.

  - **Viaje imposible**: esta directiva perfila el entorno y desencadena alertas cuando se detectan actividades del mismo usuario en ubicaciones diferentes dentro de un período de tiempo más corto que el tiempo de viaje esperado entre las dos ubicaciones. Esto podría indicar que un usuario diferente usa las mismas credenciales. La detección de este comportamiento anómalo requiere un período de aprendizaje inicial de siete días durante el cual aprende el patrón de actividad de un nuevo usuario.

  - **Actividad suplantada inusual (por usuario):** esta directiva perfila el entorno y desencadena alertas cuando los usuarios realizan varias actividades suplantadas en una sola sesión con respecto a la línea de base aprendida, lo que podría indicar un intento de infracción.

- Use una herramienta como [Office 365 Puntuación de seguridad](https://securescore.office.com/) para administrar los comportamientos y las configuraciones de seguridad de la cuenta.

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: Mantener los clientes Outlook al día

Las versiones totalmente actualizadas y revisadas de Outlook 2013 y 2016 deshabilitan la acción de formulario o regla "Iniciar aplicación" de forma predeterminada. Esto garantizará que, incluso si un atacante infringe la cuenta, se bloquearán las acciones de regla y formulario. Puede instalar las actualizaciones más recientes y las revisiones de seguridad siguiendo los pasos descritos en [Instalación de actualizaciones Office](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).

Estas son las versiones de revisión para los clientes de Outlook 2013 y 2016:

- **Outlook 2016**: 16.0.4534.1001 o superior.

- **Outlook 2013**: 15.0.4937.1000 o superior.

Para obtener más información sobre las revisiones de seguridad individuales, consulte:

- [revisión de seguridad de Outlook 2016](https://support.microsoft.com/help/3191883)

- [revisión de seguridad de Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Tercero: Supervisión de los clientes de Outlook

Tenga en cuenta que incluso con las revisiones y actualizaciones instaladas, es posible que un atacante cambie la configuración de la máquina local para volver a habilitar el comportamiento "Iniciar aplicación". Puede usar [Advanced directiva de grupo Management](/microsoft-desktop-optimization-pack/agpm/) para supervisar y aplicar directivas de máquina local en los clientes.

Puede ver si se ha vuelto a habilitar "Iniciar aplicación" mediante una invalidación en el Registro mediante la información de [Cómo ver el registro del sistema mediante versiones de 64 bits de Windows](https://support.microsoft.com/help/305097). Compruebe estas subclaves:

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Busque la clave EnableUnsafeClientMailRules. Si está allí y se establece en 1, se ha invalidado la revisión de seguridad de Outlook y el equipo es vulnerable al ataque Formulario/Reglas. Si el valor es 0, se deshabilita la acción "Iniciar aplicación". Si la versión actualizada y revisada de Outlook está instalada y esta clave del Registro no está presente, un sistema no es vulnerable a estos ataques.

Los clientes con instalaciones de Exchange locales deben considerar la posibilidad de bloquear versiones anteriores de Outlook que no tienen revisiones disponibles. Puede encontrar más información sobre este proceso en el artículo [Configurar Outlook bloqueo de cliente](/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteger Microsoft 365 como un profesional de la ciberseguridad

Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios. Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.

- Tareas a realizar en los primeros 30 días. Tienen un efecto inmediato y tienen un impacto bajo para los usuarios.

- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.

- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también:

- [Las reglas de Outlook malintencionadas](https://silentbreaksecurity.com/malicious-outlook-rules/) de SilentBreak Security Post acerca del vector de reglas proporcionan una revisión detallada de cómo las reglas de Outlook.

- [MAPI sobre HTTP y Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) en el blog de Sensepost sobre Mailrule Pwnage describe una herramienta denominada Ruler que le permite aprovechar los buzones de correo a través de Outlook reglas.

- [Outlook formularios y shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) en el blog de Sensepost sobre el vector de amenazas de formularios.

- [Código base de regla](https://github.com/sensepost/ruler)

- [Indicadores de compromiso de la regla](https://github.com/sensepost/notruler/blob/master/iocs.md)
