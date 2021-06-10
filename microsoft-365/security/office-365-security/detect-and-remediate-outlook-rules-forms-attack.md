---
title: Detectar y corregir los ataques de Outlook y las inserciones de formularios personalizados.
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
description: Obtenga información sobre cómo reconocer y corregir los ataques de Outlook y las inserciones de formularios personalizados en Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205922"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Detectar y corregir Outlook reglas y ataques de inserciones de formularios personalizados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Resumen** Obtenga información sobre cómo reconocer y corregir las reglas Outlook y los ataques de inserciones de formularios personalizados en Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>¿Cuál es el Outlook de inyección de reglas y formularios personalizados?

Después de que un atacante obtenga acceso a su organización, intentará establecer un punto de apoyo para permanecer o volver a entrar después de que se hayan descubierto. Esta actividad se denomina *establecer un mecanismo de persistencia*. Hay dos formas en que un atacante puede usar Outlook establecer un mecanismo de persistencia:

- Mediante la explotación Outlook reglas.
- Insertando formularios personalizados en Outlook.

Reinstalar Outlook o incluso darle a la persona afectada un equipo nuevo no le ayudará. Cuando la instalación nueva de Outlook se conecta al buzón, todas las reglas y formularios se sincronizan desde la nube. Las reglas o formularios suelen estar diseñados para ejecutar código remoto e instalar malware en el equipo local. El malware roba credenciales o realiza otra actividad ilícita.

La buena noticia es: si mantienes los clientes de Outlook parcheados a la versión más reciente, no eres vulnerable a la amenaza, ya que los valores predeterminados de Outlook cliente bloquean ambos mecanismos.

Los ataques suelen seguir estos patrones:

**El exploit de reglas**:

1. El atacante roba las credenciales de un usuario.

2. El atacante inicia sesión en el buzón de correo Exchange usuario (Exchange Online o local Exchange).

3. El atacante crea una regla de la Bandeja de entrada de reenvío en el buzón. La regla de reenvío se desencadena cuando el buzón recibe un mensaje específico del atacante que coincide con las condiciones de la regla. Las condiciones de regla y el formato del mensaje se personalizan entre sí.

4. El atacante envía el correo electrónico desencadenador al buzón de correo en peligro, que el usuario desprevenido sigue utilizando de forma normal.

5. Cuando el buzón recibe un mensaje que coincide con las condiciones de regla, se aplica la acción de la regla. Normalmente, la acción de regla es iniciar una aplicación en un servidor remoto (WebDAV).

6. Normalmente, la aplicación instala malware en el equipo del usuario (por ejemplo, [PowerShell Empire](https://www.powershellempire.com/)).

7. El malware permite al atacante robar (o robar de nuevo) el nombre de usuario y la contraseña del usuario u otras credenciales de la máquina local y realizar otras actividades malintencionadas.

**El exploit de formularios**:

1. El atacante roba las credenciales de un usuario.

2. El atacante inicia sesión en el buzón de correo Exchange usuario (Exchange Online o local Exchange).

3. El atacante inserta una plantilla de formulario de correo personalizada en el buzón del usuario. El formulario personalizado se desencadena cuando el buzón recibe un mensaje específico del atacante que requiere que el buzón cargue el formulario personalizado. El formulario personalizado y el formato del mensaje están hechos a medida entre sí.

4. El atacante envía el correo electrónico desencadenador al buzón de correo en peligro, que el usuario desprevenido sigue utilizando de forma normal.

5. Cuando el buzón recibe el mensaje, el buzón carga el formulario necesario. El formulario inicia una aplicación en un servidor remoto (WebDAV).

6. Normalmente, la aplicación instala malware en el equipo del usuario (por ejemplo, [PowerShell Empire](https://www.powershellempire.com/)).

7. El malware permite al atacante robar (o robar de nuevo) el nombre de usuario y la contraseña del usuario u otras credenciales de la máquina local y realizar otras actividades malintencionadas.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>¿Qué aspecto podría tener un ataque de inyección de reglas y formularios personalizados Office 365?

Es poco probable que los usuarios noten estos mecanismos de persistencia y, en algunos casos, incluso pueden ser invisibles para ellos. Este artículo le indica cómo buscar cualquiera de los siete signos (Indicadores de compromiso) que se enumeran a continuación. Si encuentra alguno de estos, debe realizar los pasos de corrección.

- **Indicadores de la transacción reglas:**
  - Acción de regla es iniciar una aplicación.
  - Regla Hace referencia a una DIRECCIÓN URL, ZIP o EXE.
  - En el equipo local, busque nuevos inicios de proceso que se originan a partir Outlook PID.

- **Indicadores de la transacción de formularios personalizados:**
  - Formularios personalizados presentes guardados como su propia clase de mensaje.
  - La clase Message contiene código ejecutable.
  - Normalmente, los formularios malintencionados se almacenan en carpetas de la Biblioteca de formularios personales o de la Bandeja de entrada.
  - El formulario se denomina IPM. Nota. [nombre personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Pasos para encontrar signos de este ataque y confirmarlo

Puede usar cualquiera de los siguientes métodos para confirmar el ataque:

- Examine manualmente las reglas y los formularios de cada buzón mediante el Outlook cliente. Este método es exhaustivo, pero solo puede comprobar un buzón a la vez. Este método puede llevar mucho tiempo si tiene muchos usuarios que comprobar y también puede infectar el equipo que está usando.

- Use el [ scriptGet-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell para volcar automáticamente todas las reglas de reenvío de correo y los formularios personalizados para todos los usuarios del arrendamiento. Este es el método más rápido y seguro con la menor cantidad de sobrecarga.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmar el ataque de reglas mediante el Outlook cliente

1. Abra los usuarios Outlook cliente como el usuario. Es posible que el usuario necesite su ayuda para examinar las reglas de su buzón.

2. Consulte Manage [email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.

3. Busque reglas que el usuario no ha creado o reglas inesperadas o con nombres sospechosos.

4. Busque en la descripción de la regla acciones de regla que se inician y se aplica o hacen referencia a un .EXE, .ZIP archivo o al inicio de una dirección URL.

5. Busque los nuevos procesos que comiencen a usar el Outlook de proceso. Consulte [Buscar el identificador de proceso](/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Pasos para confirmar el ataque de formularios mediante el Outlook cliente

1. Abra el usuario Outlook cliente como el usuario.

2. Siga los pasos descritos en [Mostrar la pestaña Programador](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) para la versión del usuario de Outlook.

3. Abra la pestaña desarrollador ahora visible en Outlook y haga clic **en Diseñar un formulario**.

4. Seleccione la **Bandeja de entrada** de la lista **Buscar** en. Busque los formularios personalizados. Los formularios personalizados son lo suficientemente raros como para que, si tiene algún formulario personalizado en absoluto, valga la pena una mirada más profunda.

5. Investigue los formularios personalizados, especialmente los marcados como ocultos.

6. Abra los formularios personalizados y, en el **grupo Formulario,** haga clic en **Ver** código para ver qué se ejecuta cuando se carga el formulario.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Pasos para confirmar el ataque de reglas y formularios con PowerShell

La forma más sencilla de comprobar un ataque [](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) de reglas o formularios personalizados es ejecutarGet-AllTenantRulesAndForms.ps1script de PowerShell. Este script se conecta a todos los buzones del inquilino y descarga todas las reglas y formularios en dos .csv archivos.

#### <a name="pre-requisites"></a>Requisitos previos

Deberá tener derechos de administrador global para ejecutar el script porque el script se conecta a todos los buzones del arrendamiento para leer las reglas y los formularios.

1. Inicie sesión en el equipo desde el que ejecutará el script con derechos de administrador local.

2. Descargue o copie el script Get-AllTenantRulesAndForms.ps1 de GitHub a una carpeta desde la que lo ejecutará. El script creará dos archivos con fecha y marca en esta carpeta, MailboxFormsExport-yyyy-mm-dd.csv y MailboxRulesExport-yyyy-mm-dd.csv.

3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.

4. Ejecute esta línea de comandos de PowerShell de la siguiente `.\Get-AllTenantRulesAndForms.ps1` manera.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretación de la salida

- **MailboxRulesExport-*yyyy-mm-dd*.csv:** Examine las reglas (una por fila) para ver las condiciones de acción que incluyen aplicaciones o ejecutables:

  - **ActionType (columna A):** si ve el valor "ID_ACTION_CUSTOM", es probable que la regla sea malintencionada.

  - **IsPotentiallyMalicious (columna D):** si este valor es "TRUE", es probable que la regla sea malintencionada.

  - **ActionCommand (columna G):** si esta columna enumera una aplicación o cualquier archivo con extensiones .exe o .zip, o una entrada desconocida que hace referencia a una dirección URL, es probable que la regla sea malintencionada.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: En general, el uso de formularios personalizados es poco frecuente. Si encuentra alguno en este libro, abra el buzón de ese usuario y examine el propio formulario. Si su organización no lo ha puesto allí intencionadamente, es probable que sea malintencionado.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Cómo detener y corregir el ataque Outlook reglas y formularios

Si encuentra alguna evidencia de cualquiera de estos ataques, la corrección es sencilla, simplemente elimine la regla o el formulario del buzón. Puede hacerlo con el cliente Outlook o con PowerShell remoto para quitar reglas.

### <a name="using-outlook"></a>Uso de Outlook

1. Identifique todos los dispositivos que el usuario ha usado con Outlook. Todos ellos tendrán que limpiarse de posible malware. No permita que el usuario inicie sesión y use el correo electrónico hasta que se limpien todos los dispositivos.

2. Sigue los pasos de [Eliminar una regla](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) para cada dispositivo.

3. Si no estás seguro de la presencia de otro malware, puedes dar formato y reinstalar todo el software del dispositivo. Para dispositivos móviles, puedes seguir los pasos de los fabricantes para restablecer el dispositivo a la imagen de fábrica.

4. Instale las versiones más actualizadas de Outlook. Recuerde que la versión actual de Outlook bloquea ambos tipos de este ataque de forma predeterminada.

5. Una vez que se hayan quitado todas las copias sin conexión del buzón de correo, restablezca la contraseña del usuario (use una de alta calidad) y siga los pasos descritos en Configurar la autenticación [multifactor](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) para los usuarios si MFA aún no se ha habilitado. Esto garantiza que las credenciales del usuario no se exponen a través de otros medios (como suplantación de identidad o volver a usar la contraseña).

### <a name="using-powershell"></a>Con PowerShell

Hay dos cmdlets de PowerShell remotos que puede usar para quitar o deshabilitar reglas peligrosas. Solo tienes que seguir los pasos.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Pasos para buzones de correo que se encuentran en un Exchange servidor

1. Conectar al servidor Exchange con PowerShell remoto. Siga los pasos descritos [en Conectar para Exchange con PowerShell remoto.](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Si desea quitar por completo una sola regla, varias reglas o todas las reglas de un buzón, use el cmdlet [Remove-InboxRule.](/powershell/module/exchange/Remove-InboxRule)

3. Si desea conservar la regla y su contenido para una investigación posterior, use el cmdlet [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Pasos para buzones en Exchange Online

1. Siga los pasos de [Conectar para Exchange Online con PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Si desea quitar por completo una sola regla, varias reglas o todas las reglas de un buzón, use el cmdlet [Remove-Inbox Rule.](/powershell/module/exchange/Remove-InboxRule)

3. Si desea conservar la regla y su contenido para una investigación posterior, use el cmdlet [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Cómo minimizar ataques futuros

### <a name="first-protect-your-accounts"></a>En primer lugar: proteger sus cuentas

Las vulnerabilidades de reglas y formularios solo las usa un atacante después de haber robado o infringido una de las cuentas del usuario. Por lo tanto, el primer paso para evitar el uso de estas vulnerabilidades en su organización es proteger agresivamente sus cuentas de usuario. Algunas de las formas más comunes de vulneración de cuentas son a través de ataques de phishing o [de spray de contraseña.](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)

La mejor manera de proteger las cuentas de usuario y, especialmente, las cuentas de administrador, es configurar la autenticación [multifactor para los usuarios.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) También debe:

- Supervisar cómo se accede a las [cuentas de usuario y cómo se usa](/azure/active-directory/active-directory-view-access-usage-reports). Es posible que no impida la infracción inicial, pero acortará la duración y el impacto de la infracción al detectarla antes. Puede usar estas directivas [de Office 365 Cloud App Security para](/cloud-app-security/what-is-cloud-app-security) supervisar sus cuentas y alertar sobre actividades inusuales:

  - **Varios intentos de** inicio de sesión con errores: esta directiva perfila el entorno y desencadena alertas cuando los usuarios realizan varias actividades de inicio de sesión con errores en una sola sesión con respecto a la línea base aprendida, lo que podría indicar un intento de infracción.

  - **Viajes imposibles:** esta directiva perfila el entorno y desencadena alertas cuando se detectan actividades del mismo usuario en diferentes ubicaciones en un período de tiempo que es menor que el tiempo de viaje esperado entre las dos ubicaciones. Esto podría indicar que un usuario diferente usa las mismas credenciales. La detección de este comportamiento anómalo requiere un período de aprendizaje inicial de siete días durante el cual se aprende el patrón de actividad de un nuevo usuario.

  - Actividad suplantada inusual **(por usuario):** esta directiva perfila el entorno y desencadena alertas cuando los usuarios realizan varias actividades suplantadas en una sola sesión con respecto a la línea base aprendida, lo que podría indicar un intento de infracción.

- Usa una herramienta como [Office 365 puntuación segura para](https://securescore.office.com/) administrar los comportamientos y configuraciones de seguridad de la cuenta.

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: Mantener sus clientes Outlook actuales

Las versiones actualizadas y parcheadas de Outlook 2013 y 2016 deshabilitan la acción de regla o formulario "Iniciar aplicación" de forma predeterminada. Esto garantizará que incluso si un atacante infringe la cuenta, se bloquearán las acciones de regla y formulario. Puede instalar las actualizaciones y revisiones de seguridad más recientes siguiendo los pasos descritos en [Instalar Office actualizaciones.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Estas son las versiones de revisión para Outlook clientes de 2013 y 2016:

- **Outlook 2016**: 16.0.4534.1001 o posterior.

- **Outlook 2013**: 15.0.4937.1000 o posterior.

Para obtener más información sobre las revisiones de seguridad individuales, vea:

- [Outlook 2016 Revisión de seguridad](https://support.microsoft.com/help/3191883)

- [Outlook de seguridad de 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Tercero: Supervisar los clientes Outlook cliente

Tenga en cuenta que incluso con las revisiones y actualizaciones instaladas, es posible que un atacante cambie la configuración de la máquina local para volver a habilitar el comportamiento de "Iniciar aplicación". Puede usar la [Administración avanzada de directivas de grupo](/microsoft-desktop-optimization-pack/agpm/) para supervisar y aplicar directivas de máquina local en sus clientes.

Puede ver si "Iniciar aplicación" se ha habilitado de nuevo a través de una invalidación en el Registro mediante la información de Cómo ver el Registro del sistema mediante versiones de [64](https://support.microsoft.com/help/305097)bits de Windows . Compruebe estas subclaves:

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Busque la clave EnableUnsafeClientMailRules. Si está ahí y se establece en 1, se ha invalidado la revisión de seguridad Outlook y el equipo es vulnerable al ataque Formulario/Reglas. Si el valor es 0, la acción "Iniciar aplicación" está deshabilitada. Si la versión actualizada y con revisión de Outlook está instalada y esta clave del Registro no está presente, un sistema no es vulnerable a estos ataques.

Los clientes con instalaciones Exchange locales deben considerar el bloqueo de versiones anteriores de Outlook que no tienen revisiones disponibles. Los detalles sobre este proceso se pueden encontrar en el artículo [Configure Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteger Microsoft 365 como un profesional de la ciberseguridad

Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios. Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.

- Tareas a realizar en los primeros 30 días. Estos tienen efecto inmediato y tienen un impacto bajo para los usuarios.

- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.

- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también:

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector proporciona una revisión detallada de cómo se Outlook reglas.

- MAPI sobre HTTP y [Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) en el blog sensepost sobre Mailrule Pwnage analiza una herramienta denominada Ruler que le permite aprovechar buzones a través de Outlook reglas.

- [Outlook formularios y shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) en el blog sensepost sobre el vector de amenazas de formularios.

- [Ruler Codebase](https://github.com/sensepost/ruler)

- [Indicadores de regla de compromiso](https://github.com/sensepost/notruler/blob/master/iocs.md)