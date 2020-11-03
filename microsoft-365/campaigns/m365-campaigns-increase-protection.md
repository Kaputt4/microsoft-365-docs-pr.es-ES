---
title: Aumentar la protección contra amenazas
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Obtener ayuda para aumentar el nivel de protección en Microsoft 365
ms.openlocfilehash: 99b9bfac7867d6f6b29571940f717667fd05a697
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843261"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Aumentar la protección contra amenazas para la suscripción a Microsoft 365

Este artículo le ayuda a aumentar la protección en su suscripción de Microsoft 365 para protegerse contra phishing, malware y otras amenazas. Estas recomendaciones son adecuadas para organizaciones con mayor necesidad de seguridad, como campañas políticas, oficinas de abogados e clínicas de atención médica.

Antes de empezar, Compruebe la puntuación segura de Microsoft. La puntuación segura de Microsoft analiza la seguridad de la organización en función de las actividades habituales y la configuración de seguridad y asigna una puntuación. Empiece por tomar nota del resultado actual. La realización de las acciones recomendadas en este artículo aumenta su puntuación. El objetivo no es conseguir la puntuación máxima, sino que debe tener en cuenta las oportunidades para proteger su entorno que no afectan negativamente a la productividad de los usuarios.

Para obtener más información, consulte [calificación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar el nivel de protección contra malware en correo

El entorno de Office 365 o Microsoft 365 incluye protección contra malware, pero puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. Para subir la protección contra malware en el correo electrónico:

1. Vaya a <https://protection.office.com> e inicie sesión con las credenciales de su cuenta de administrador.

2. En el centro de navegación de la & de seguridad, en el panel de navegación izquierdo, en **Administración de amenazas** , elija **Directiva** \> **antimalware** de directiva.

3. Haga doble clic en la directiva predeterminada para editar esta directiva de toda la compañía.

4. Haga clic en **Configuración**.

5. En **filtro de tipos de datos adjuntos comunes** , seleccione **activado**. Los tipos de archivo que están bloqueados aparecen en la ventana que se encuentra justo debajo de este control. Asegúrese de agregar estos FileTypes:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Puede Agregar o eliminar tipos de archivo más adelante, si es necesario.

6. Haga clic en **Guardar**.

Para obtener más información, vea [protección contra malware en EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="protect-against-ransomware"></a>Protección contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de los archivos o el bloqueo de las pantallas del equipo. A continuación, intenta extort dinero de víctimas solicitando "Ransom", normalmente en forma de cryptocurrencies como bitcoin, en Exchange para tener acceso a los datos.

Puede proteger contra ransomware si crea una o más reglas de flujo de correo para bloquear extensiones de archivo que se usan con frecuencia para ransomware (estos se agregaron en el paso [aumentar el nivel de protección contra malware en el correo](#raise-the-level-of-protection-against-malware-in-mail) ) o para advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.

Además de los archivos bloqueados en el paso anterior, también es aconsejable crear una regla para advertir a los usuarios antes de abrir datos adjuntos de archivos de Office que incluyan macros. Ransomware puede estar oculto dentro de las macros, así que advierta a los usuarios que no abran estos archivos de personas que no conocen.

Para crear una regla de transporte de correo:

1. Vaya al centro de administración en <https://admin.microsoft.com> y elija **centros de administración** \> **Exchange**.

2. En la categoría **flujo de correo** , haga clic en **reglas**.

3. Haga clic en **+** y, a continuación, haga clic en **crear una nueva regla**.

4. Haga clic en **más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la siguiente tabla para la regla. Deje el resto de las opciones de configuración en el valor predeterminado, a menos que quiera cambiarlas.

6. Haga clic en **Guardar**.

|Configuración|Advertir a los usuarios antes de abrir datos adjuntos de archivos de Office|
|---|---|
|Nombre|Regla antiransomware: advertir a los usuarios|
|Aplicar esta regla si. . .|Los datos adjuntos. . . coincidencias de extensión de archivo. . .|
|Especificar palabras o frases|Agregue estos tipos de archivo: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Haga lo siguiente. . .|Notificar al destinatario con un mensaje|
|Proporcionar el texto del mensaje|No abra estos tipos de archivos de personas que no sabe porque podrían contener macros con código malintencionado.|

Para obtener más información, vea:

- [Ransomware: Cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar su OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático de correo electrónico

Los hackers que obtienen acceso al buzón de un usuario pueden robar el correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin la conciencia del usuario. Puede evitar que esto suceda mediante la configuración de una regla de flujo de correo.

Para crear una regla de transporte de correo, vea [este breve vídeo](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) o siga estos pasos:

1. En el centro de administración de Microsoft 365, haga clic en **centros de administración** \> **Exchange**.

2. En la categoría **flujo de correo** , haga clic en **reglas**.

3. Haga clic en **+** y, a continuación, haga clic en **crear una nueva regla**.

4. Haga clic en **más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la tabla siguiente. Deje el resto de las opciones de configuración en el valor predeterminado, a menos que quiera cambiarlas.

6. Haga clic en **Guardar**.

|Configuración|Advertir a los usuarios antes de abrir datos adjuntos de archivos de Office|
|---|---|
|Nombre|Impedir el reenvío automático de correo electrónico a dominios externos|
|Aplicar esta regla si...|El remitente. . . es externo/interno. . . Dentro de la organización|
|Agregar condición|Las propiedades del mensaje. . . incluir el tipo de mensaje. . . Reenvío automático|
|Haga lo siguiente...|Bloquear el mensaje. . . rechazar el mensaje e incluir una explicación.|
|Proporcionar el texto del mensaje|El reenvío automático de correo electrónico fuera de esta organización se impide por motivos de seguridad.|

## <a name="protect-your-email-from-phishing-attacks"></a>Proteger el correo electrónico de ataques de suplantación de identidad

Si ha configurado uno o más dominios personalizados para el entorno de Office 365 o Microsoft 365, puede configurar la protección contra suplantas de identidad (phishing) dirigida. Protección contra suplantación de identidad (phishing), parte de Microsoft defender para Office 365, puede ayudar a proteger a su organización de ataques de suplantación de identidad (phishing) malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario que lo haga.

Le recomendamos que empiece con esta protección creando una directiva para proteger a los usuarios más importantes y a su dominio personalizado.

Para crear una directiva contra la suplantación de identidad en defender para Office 365, vea [este breve vídeo de aprendizaje](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)o siga los pasos que se indican a continuación:

1. Vaya a <https://protection.office.com>.

2. En el centro de navegación de la & de seguridad, en el panel de navegación izquierdo, en **Administración de amenazas** , elija **Directiva**.

3. En la página **Directiva** , elija **anti-phishing**.

4. En la página **contra la suplantación de identidad** , seleccione **+ crear**. Se inicia un asistente que le guía por el proceso de definición de la Directiva antiphishing.

5. Especifique el nombre, la descripción y la configuración de la Directiva tal y como se recomienda en el siguiente gráfico. Para obtener más información, vea [información sobre la Directiva contra la suplantación de identidad en Microsoft defender para Office 365 opciones](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. Una vez que haya revisado la configuración, elija **crear esta directiva** o **Guardar** , según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Dominio y personal de la campaña más valioso|
|Description|Asegúrese de que el personal más importante y nuestro dominio no se están suplantando.|
|Agregar usuarios que proteger|Seleccionar **+ Agregar condición, el destinatario es**. Escriba los nombres de usuario o escriba la dirección de correo electrónico del candidato, el administrador de campañas y otros miembros importantes del personal. Puede Agregar hasta 20 direcciones internas y externas que desee proteger de la suplantación.|
|Agregar dominios que proteger|Seleccionar **+ Agregar una condición, el dominio del destinatario es**. Escriba el dominio personalizado asociado con la suscripción de Microsoft 365, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía un correo electrónico: elija **redirigir un mensaje a otra dirección de correo electrónico** y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *alicia <span> <span> @contoso. com*. <br/> Si el correo electrónico lo envía un dominio suplantado: elija **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|Aquí puede agregar sus propios dominios o cualquier otro dominio de confianza.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos** , seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla de verificación situada junto al nombre del dominio, por ejemplo, *contoso. <span> <span> com* , en la lista y, a continuación, seleccione **Agregar**. Seleccione **Listo**.|

Para obtener más información, vea [set up anti-phishing policies in defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Protección contra datos adjuntos malintencionados, archivos y vínculos con defender para Office 365

![Pancarta que apunta a https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

En primer lugar, asegúrese de que en el centro de administración de <https://admin.microsoft.com> tenga activada la nueva vista previa del centro de administración. Active la alternancia junto al texto **nuevo centro de administración**.

   ![La nueva vista previa del centro de administración.](../media/previewon.png)

Si aún no ve la página **configuración** con tarjetas en su inquilino, vea cómo completar estos pasos en seguridad & el centro de cumplimiento. Consulte [configurar datos adjuntos seguros en el centro de seguridad & cumplimiento](#set-up-safe-attachments-in-the-security--compliance-center) y [configurar vínculos seguros en el centro de seguridad & cumplimiento](#set-up-safe-links-in-the-security--compliance-center).

1. En el panel de navegación izquierdo, elija **instalar**.
2. En la página **configuración** , elija **Ver** en la ficha **aumentar protección frente a amenazas avanzadas** .

   ![Elija Ver en el aumentar protección frente a amenazas avanzadas.](../media/startatp.png)

3. En la página **aumentar la protección desde amenazas avanzadas** , **Elija introducción**.
4. En el panel que se abre, active las casillas situadas junto a **vínculos y datos adjuntos en el correo electrónico** , **analizar archivos en SharePoint, OneDrive y Microsoft Teams** , y **examinar los vínculos de las aplicaciones de escritorio y Office online de Office** en **buscar contenido malintencionado**.

   En **vínculos y datos adjuntos en el correo electrónico** , escriba todos los usuarios o los usuarios específicos cuyo correo electrónico desea examinar.

   ![Active todas las casillas de verificación en aumentar protección frente a amenazas avanzadas.](../media/setatp.png)

5. Elija **crear directivas** para activar los datos adjuntos seguros y vínculos seguros.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Configurar datos adjuntos seguros en el centro de seguridad & cumplimiento

Los usuarios envían, reciben y comparten con regularidad datos adjuntos, como documentos, presentaciones, hojas de cálculo, etc. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados solo mirando un mensaje de correo electrónico. Microsoft defender para Office 365 incluye protección de datos adjuntos seguros, pero esta protección no está activada de forma predeterminada. Le recomendamos que cree una nueva regla para comenzar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

Para crear una directiva de datos adjuntos seguros, vea [este breve vídeo](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o siga los pasos que se indican a continuación:

1. Vaya a <https://protection.office.com> e inicie sesión con su cuenta de administrador.

2. En el centro de navegación de la & de seguridad, en el panel de navegación izquierdo, en **Administración de amenazas** , elija **Directiva**.

3. En la página Directiva, elija **datos adjuntos seguros**.

4. En la página datos adjuntos seguros, aplique esta protección ampliando la selección de la casilla **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .

5. Seleccione esta **+** Directiva para crear una nueva Directiva.

6. Aplique la configuración de la tabla siguiente.

7. Una vez que haya revisado la configuración, elija **crear esta directiva** o **Guardar** , según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Bloquear los correos electrónicos actuales y futuros con malware detectado.|
|Description|Bloquear los mensajes de correo electrónico y datos adjuntos futuros y futuros con malware detectado.|
|Guardar datos adjuntos respuesta de malware desconocida|Seleccione **bloquear: bloquear los correos electrónicos y datos adjuntos actuales y futuros con malware detectado**.|
|Redirigir datos adjuntos en detección|Habilitar redirección (Seleccione esta casilla) <br/> Escriba la cuenta de administrador o una configuración de buzón para la cuarentena. <br/> Aplique la selección anterior si se produce un error de análisis de malware para datos adjuntos de tiempo de espera o error (Active esta casilla).|
|Aplicado a|El dominio del destinatario es. . . Seleccione su dominio.|

Para obtener más información, vea [set up anti-phishing policies in defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Configurar vínculos seguros en el centro de seguridad & cumplimiento

A veces, los hackers ocultan sitios Web malintencionados en vínculos de correo electrónico u otros archivos. Vínculos seguros, parte de Microsoft defender para Office 365, puede ayudarle a proteger su organización proporcionando una comprobación del tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos de Office. La protección se define mediante directivas de vínculos a prueba de errores.

Le recomendamos que haga lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva Directiva dirigida a todos los destinatarios de su dominio.

Para configurar vínculos seguros, vea [este vídeo de aprendizaje corto](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)o realice los pasos siguientes:

1. Vaya a <https://protection.office.com> e inicie sesión con su cuenta de administrador.

2. En el centro de navegación de la & de seguridad, en el panel de navegación izquierdo, en **Administración de amenazas** , elija **Directiva**.

3. En la página Directiva, elija **vínculos seguros**.

Para modificar la directiva predeterminada:

1. En la página vínculos seguros, en **directivas que se aplican a toda la organización** , seleccione la directiva **predeterminada** .

2. En **configuración que se aplica al contenido excepto al correo electrónico** , seleccione **Microsoft 365 apps for Enterprise, Office para iOS y Android**.

3. Haga clic en **Guardar**.

Para crear una nueva Directiva dirigida a todos los destinatarios de su dominio:

1. En la página vínculos seguros, en **directivas que se aplican a toda la organización** , haga clic en **+** para crear una nueva Directiva.

2. Aplique la configuración que se muestra en la tabla siguiente.

3. Haga clic en **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Directiva de vínculos seguros para todos los destinatarios del dominio|
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Seleccione **activado: las direcciones URL se rescribirán y comprobarán con una lista de vínculos malintencionados conocidos cuando el usuario haga clic en el vínculo**.|
|Usar datos adjuntos seguros para analizar contenido descargable|Seleccione esta casilla.|
|Aplicado a|El dominio del destinatario es. . . Seleccione su dominio.|

Para obtener más información, vea [vínculos a prueba de errores en defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="turn-on-the-unified-audit-log"></a>Activar el registro de auditoría unificado

Después de activar la búsqueda de registros de auditoría en el centro de seguridad & cumplimiento, puede conservar el administrador y la actividad de otros usuarios en el registro y realizar búsquedas en él.

Debe tener asignado el rol registros de auditoría en Exchange Online para activar o desactivar la búsqueda de registros de auditoría en su suscripción de Microsoft 365. De forma predeterminada, este rol se asigna a los grupos de roles administración de cumplimiento y administración de la organización en la página permisos del centro de administración de Exchange. Los administradores globales de Microsoft 365 son miembros de este grupo de forma predeterminada.

1. Para activar la búsqueda de registros de auditoría, vaya al centro de administración en <https://admin.microsoft.com> y, a continuación, elija **cumplimiento** en **centros de administración** en el panel de navegación izquierdo.
2. En la página **Microsoft 365 Compliance** , elija **más recursos** y, a continuación, **abra** en la tarjeta del **centro de & de seguridad de Office 365** .

    ![Elija abrir en los coches de cumplimiento de & de seguridad.](../media/gotosecandcomp.png)
3. En la página seguridad y cumplimiento, haga clic en **Buscar** y, a continuación, en **búsqueda de registros de auditoría**.
4. En la parte superior de la página de **búsqueda de registros de auditoría** , seleccione **Activar auditoría**.

Una vez activada la característica, puede buscar archivos, carpetas y muchas actividades. Para obtener más información, vea [Buscar en el registro de auditoría](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Ajustar la configuración de uso compartido anónimo para archivos y carpetas de SharePoint y OneDrive

(cambiar la expiración del vínculo anónimo predeterminado a 14 días, cambiar el tipo de uso compartido predeterminado a "personas específicas") Para cambiar la configuración de uso compartido para OneDrive y SharePoint:

1. Vaya al centro de administración de <https://admin.microsoft.com> y, a continuación, elija **SharePoint** en **centros de administración** en el panel de navegación izquierdo.
2. En el centro de administración de SharePoint, **Policies** vaya a \> **uso compartido** de directivas.
3. En la página de **uso compartido** , en **vínculos de archivos y carpetas** , seleccione **personas específicas** y, en **Configuración avanzada para vínculos de "cualquiera"** , seleccione **estos vínculos deben expirar dentro de estos muchos días** y escriba 14 (o cualquier otro número de días que desee restringir la duración del vínculo).

   ![Elija personas específicas y establezca expiración de vínculos en 14 días.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Alertas de actividad

Puede usar alertas de actividad para realizar un seguimiento de las actividades de administración y de usuario y detectar los incidentes de malware y prevención de pérdida de datos en la organización. La suscripción incluye un conjunto de directivas predeterminadas, pero también puede crear otras personalizadas. Para obtener más información, consulte [Alert Policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies). Por ejemplo, si almacena un archivo importante en SharePoint que no quiere que nadie comparta de forma externa, puede crear una notificación que le avise si alguien lo comparte.

La siguiente figura muestra las directivas predeterminadas que se incluyen en Microsoft 365.

![Directivas de alertas predeterminadas incluidas en Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Deshabilitar o administrar el uso compartido de calendarios

Puede impedir que los usuarios de su organización compartan sus calendarios o también puede administrar lo que pueden compartir. Por ejemplo, puede restringir el uso compartido solo a horas de disponibilidad.

1. Vaya al centro de administración en <https://admin.microsoft.com> y elija **parámetros de configuración** de los \> **servicios & complementos**.
2. En la página **servicios de & complementos** , elija **calendario** y elija si los usuarios de su organización pueden compartir sus calendarios con usuarios ajenos a Office 365 o Exchange, o con cualquier persona.

   Si elige la opción compartir con otros usuarios, también puede optar por compartir únicamente la información de disponibilidad.

3. Elija **Guardar cambios** en la parte inferior de la página.

   En la siguiente figura se muestra el uso compartido de calendarios no permitido.

   ![Captura de pantalla que muestra el uso compartido de calendario externo como no permitido.](../media/nocalendarsharing.png)

   En la siguiente figura se muestra la configuración cuando se permite el uso compartido de calendarios con un vínculo de correo electrónico con información de disponibilidad.

   ![Captura de pantalla del uso compartido de disponibilidad del calendario con cualquier usuario.](../media/sharefreebusy.png)

Si los usuarios pueden compartir sus calendarios, vea [estas instrucciones](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) sobre cómo compartir desde Outlook en la Web.
