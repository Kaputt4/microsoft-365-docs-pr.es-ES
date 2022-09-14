---
title: Aumentar la protección contra amenazas para Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- VSBFY23
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
description: Configure Microsoft Defender para Office 365 y proteja los datos confidenciales contra phishing, malware y otras amenazas.
ms.openlocfilehash: 41eed29cdc87e4334270efdb4d0039147254988c
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67661372"
---
# <a name="increase-threat-protection-for-microsoft-365-for-business"></a>Aumentar la protección contra amenazas para Microsoft 365 para empresas

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

Este artículo le ayuda a aumentar la protección en su suscripción de Microsoft 365 para protegerse contra phishing, malware y otras amenazas. Estas recomendaciones son adecuadas para las organizaciones con una mayor necesidad de seguridad, como las oficinas legales y las clínicas de atención médica.

Antes de empezar, compruebe su Office 365 Puntuación de seguridad. Office 365 Puntuación de seguridad analiza la seguridad de la organización en función de las actividades normales y la configuración de seguridad, y asigna una puntuación. Empiece por tomar nota de la puntuación actual. Para aumentar la puntuación, complete las acciones recomendadas en este artículo. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades de proteger el entorno que no afectan negativamente a la productividad de los usuarios.

Para obtener más información, consulte [Puntuación segura de Microsoft](../../security/defender/microsoft-secure-score.md).

## <a name="watch-raise-the-level-of-protection-against-malware-in-mail"></a>Ver: Aumentar el nivel de protección contra malware en el correo

El entorno de Office 365 o Microsoft 365 incluye protección contra malware. Para aumentar esta protección, bloquee los datos adjuntos con los tipos de archivo que se usan habitualmente para el malware. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OA7Z?autoplay=false]

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, elija **Mostrar más**, **Administración centros** y, a continuación, **Seguridad**.

1. Vaya a **Email &** directivas de colaboración \> **& reglas Directivas** \> de **amenazas**.

1. En las directivas disponibles, elija **Antimalware**.

Para aumentar la protección contra malware en el correo electrónico:

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, vaya a **Directivas de colaboración** \> **Email & & reglas** \> **Directivas** \> **de amenazas Antimalware** en la sección **Directivas**.

1. En la página **Antimalware**, haga doble clic en **Predeterminado (predeterminado).** Aparece un control flotante. 

1. Seleccione **Editar configuración de protección** en la parte inferior del control flotante. 

1. En **Configuración de protección**, active la casilla situada junto a **Habilitar el filtro de datos adjuntos comunes**. Los tipos de archivo bloqueados se enumeran directamente debajo de este control. Asegúrese de agregar estos tipos de archivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Para agregar o eliminar tipos de archivo, seleccione **Personalizar tipos de archivo** al final de la lista.

1. Seleccione **Guardar.**

Para obtener más información, consulte [Protección contra malware en EOP](../../security/office-365-security/anti-malware-protection.md).

## <a name="watch-protect-against-ransomware"></a>Ver: Proteger contra ransomware

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198018).

Ransomware restringe el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero de las víctimas pidiendo "rescate", normalmente en forma de criptomonedas como Bitcoin, a cambio de acceso a los datos.

Para protegerse contra ransomware, cree una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan normalmente para ransomware. (Ha agregado estas reglas en el paso [Inspección: Aumentar el nivel de protección contra malware en el correo](#watch-raise-the-level-of-protection-against-malware-in-mail) ). También puede advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.

Además de los archivos que bloqueó en el paso anterior, se recomienda crear una regla para advertir a los usuarios antes de abrir archivos adjuntos de Office que incluyan macros. Ransomware puede estar oculto dentro de macros, por lo que advertir a los usuarios que no abran estos archivos de personas que no conocen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

1. En el centro de administración de [https://admin.microsoft.com](https://admin.microsoft.com), elija **Exchange** en **Administración centros**.

1. En el menú de la izquierda, elija **Flujo de correo**.
 
1. En la pestaña Reglas, elija la flecha situada junto al símbolo más (+) y, a continuación, elija **Crear una nueva regla**.

1. En la **página nueva regla** , escriba un nombre para la regla, desplácese hasta la parte inferior y, a continuación, elija **Más opciones**.

Para crear una regla de transporte de correo:

1. Vaya al centro de administración en <https://admin.microsoft.com>y elija **Administración centros** \> **de Exchange**.

2. En la categoría **flujo de correo** , seleccione **reglas**.

3. Seleccione **+** y, a continuación, seleccione **Crear una nueva regla**.

4. Seleccione **Más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la siguiente tabla para la regla. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Haga clic en **Guardar**.

|Setting|Advertir a los usuarios antes de abrir archivos adjuntos de Office|
|---|---|
|Nombre|Regla contra ransomware: advertir a los usuarios|
|Aplique esta regla si es . . .|Cualquier archivo adjunto . . . la extensión de archivo coincide con . . .|
|Especificar palabras o frases|Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Haga lo siguiente. . .|Notificar al destinatario con un mensaje|
|Proporcionar texto del mensaje|No abra estos tipos de archivos de personas que no conozca porque podrían contener macros con código malintencionado.|

Para obtener más información, consulte:

- [Ransomware: cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restauración de OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático para correo electrónico

Los hackers que obtienen acceso al buzón de correo de un usuario pueden robar correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin el reconocimiento del usuario. Para evitar que esto suceda, configure una regla de flujo de correo.

Para crear una regla de transporte de correo, siga estos pasos:

1. En el Centro de administración de Microsoft 365, seleccione **Administración centros** \> **de Exchange**.

2. En la categoría **flujo de correo** , seleccione **reglas**.

3. Seleccione **+** y, a continuación, seleccione **Crear una nueva regla**.

4. Para ver todas las opciones, seleccione **Más opciones** en la parte inferior del cuadro de diálogo.

5. Aplique la configuración de la tabla siguiente. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Haga clic en **Guardar**.

|Setting|Advertir a los usuarios antes de abrir archivos adjuntos de Office|
|---|---|
|Nombre|Impedir el reenvío automático de correo electrónico a dominios externos|
|Aplique esta regla si ...|Remitente . . . es externo o interno. . . Dentro de la organización|
|Agregar condición|Propiedades del mensaje . . . incluya el tipo de mensaje . . . Reenvío automático|
|Haga lo siguiente...|Bloquee el mensaje . . . rechazar el mensaje e incluir una explicación.|
|Proporcionar texto del mensaje|Se impide el reenvío automático de correo electrónico fuera de esta organización por motivos de seguridad.|

## <a name="watch-protect-your-email-from-phishing-attacks"></a>Inspección: Protección del correo electrónico frente a ataques de suplantación de identidad

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198014).

Si ha configurado uno o varios dominios personalizados para el entorno de Office 365 o Microsoft 365, puede configurar la protección contra phishing dirigida. La protección contra suplantación de identidad (phishing), que forma parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización frente a ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.

Se recomienda empezar a trabajar con esta protección mediante la creación de una directiva para proteger a los usuarios más importantes y a su dominio personalizado.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.

2. Vaya a Email & **directivas de** **colaboración** \> & reglas \> **Directivas** \> **de amenazas Anti-phishing** en la sección **Directivas**.

3. En la página **Anti-phishing** , seleccione **+ Crear**. Se inicia un asistente que le guiará a través de la definición de la directiva anti-phishing.

4. Especifique el nombre, la descripción y la configuración de la directiva como se recomienda en la tabla siguiente. Para obtener más información, consulte [Más información sobre la directiva contra suplantación de identidad (phishing) en Microsoft Defender para Office 365 opciones](../../security/office-365-security/set-up-anti-phishing-policies.md).

5. Después de revisar la configuración, elija **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Dominio y personal de campaña más valioso|
|Descripción|Asegúrese de que el personal más importante y nuestro dominio no se suplantan.|
|Agregar usuarios que proteger|Seleccione **+ Agregar una condición, El destinatario es**. Escriba los nombres de usuario o escriba la dirección de correo electrónico del candidato, el jefe de campaña y otros miembros importantes del personal. Puede agregar hasta 20 direcciones internas y externas que desea proteger contra la suplantación.|
|Agregar dominios que proteger|Seleccione **+ Agregar una condición; El dominio de destinatario es**. Escriba el dominio personalizado asociado a la suscripción de Microsoft 365, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía un correo electrónico: elija **Redirigir mensaje a otra dirección de correo electrónico** y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *Alice<span><span>@contoso.com*. Si el correo electrónico lo envía un dominio suplantado: elija **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|Aquí puede agregar su propio dominio o cualquier otro dominio de confianza.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos**, seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla situada junto al nombre del dominio, por ejemplo, *contoso.<span><span> com*, en la lista y, a continuación, seleccione **Agregar**. Seleccione **Listo**.|

## <a name="watch-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Vea: Protección contra archivos y datos adjuntos malintencionados con datos adjuntos seguros

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198019).

Los usuarios envían, reciben y comparten datos adjuntos con regularidad, como documentos, presentaciones, hojas de cálculo, etc. No siempre es fácil saber si un archivo adjunto es seguro o malintencionado simplemente examinando un mensaje de correo electrónico. Microsoft Defender para Office 365, anteriormente denominada ATP de Microsoft 365 o Advanced Threat Protection, incluye protección de datos adjuntos seguros, pero esta protección no está activada de forma predeterminada. Se recomienda crear una nueva regla para empezar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

1. Vaya al [centro de administración](https://admin.microsoft.com) y seleccione **Configurar**.
1. Desplácese hacia abajo hasta **Aumentar la protección frente a amenazas avanzadas**. Seleccione **Ver**, **Administrar** y, a continuación, **Datos adjuntos seguros de ATP**.
1. Seleccione la regla de datos adjuntos seguros y, a continuación, elija el icono **Editar** .
1. Seleccione **la configuración** y, a continuación, compruebe que Bloquear está seleccionado.
1. Desplácese hacia abajo. Elija **Habilitar redirección** y escriba su dirección de correo electrónico o la dirección de la persona que desea revisar los datos adjuntos bloqueados.
1. Seleccione **aplicado a** y, a continuación, seleccione el nombre de dominio.
1. Elija los dominios adicionales que posea (como el dominio de onmicrosoft.com) a los que le gustaría aplicar la regla. Seleccione **Agregar** y, a continuación, **Aceptar**.
1. Haga clic en **Guardar**.

La regla de datos adjuntos seguros de ATP se ha actualizado. Ahora que la protección está en vigor, no podrá abrir un archivo malintencionado desde Outlook, OneDrive, SharePoint o Teams. Los archivos afectados tendrán escudos rojos junto a ellos. Si alguien intenta abrir un archivo bloqueado, recibirá un mensaje de advertencia.

Una vez que la directiva haya estado en vigor durante un tiempo, visite la página Informes para ver lo que se ha examinado.

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión con su cuenta de administrador.

2. Vaya a Email & **directivas de** **colaboración** \> & reglas \> **Directivas** \> **de amenazas Antimalware** en la sección **Directivas**.

3. Seleccione **+ Crear** para crear una nueva directiva.

4. Aplique la configuración de la tabla siguiente.

5. Después de revisar la configuración, seleccione **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Bloquear correos electrónicos actuales y futuros con malware detectado.|
|Descripción|Bloquear correos electrónicos y datos adjuntos actuales y futuros con malware detectado.|
|Guardar datos adjuntos respuesta de malware desconocida|Seleccione **Bloquear: bloquee los correos electrónicos y los datos adjuntos actuales y futuros con el malware detectado**.|
|Redireccionamiento de datos adjuntos al detectar|Habilitar redirección (seleccione este cuadro) Escriba la configuración de la cuenta de administrador o de un buzón para la cuarentena.          Aplique la selección anterior si se agota el tiempo de espera de búsqueda de datos adjuntos o se produce un error (seleccione este cuadro).|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

Para obtener más información, consulte [Configuración de directivas contra suplantación de identidad en Microsoft Defender para Office 365](../../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="watch-protect-against-phishing-attacks-with-safe-links"></a>Vea: Protección contra ataques de suplantación de identidad (phishing) con vínculos seguros

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198201).

Los hackers a veces ocultan sitios web malintencionados en vínculos en el correo electrónico u otros archivos. Vínculos seguros, parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización proporcionando la verificación con el tiempo de clic de las direcciones web (DIRECCIONES URL) en mensajes de correo electrónico y documentos de Office. La protección se define mediante directivas de vínculos seguros.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender para Office 365, anteriormente denominado ATP de Microsoft 365 o Advanced Threat Protection, ayuda a proteger su empresa frente a sitios malintencionados cuando las personas hacen clic en vínculos en aplicaciones de Office.

1. Vaya al [centro de administración](https://admin.microsoft.com) y seleccione **Configurar**.

1. Desplácese hacia abajo hasta **Aumentar la protección frente a amenazas avanzadas**. Seleccione **Administrar** y, a continuación, **Vínculos seguros**.

1. Seleccione **Configuración global** y, en **Bloquear las siguientes direcciones URL**, escriba la dirección URL que desea bloquear.

Se recomienda hacer lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva directiva destinada a todos los destinatarios del dominio.

Para configurar vínculos seguros, siga estos pasos:

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión con su cuenta de administrador.

2. o para **Email &** directivas de colaboración \> **& reglas Directivas** \>  \> **de amenazas Antimalware** en la sección **Directivas**.

3. Seleccione **+ Crear** para crear una nueva directiva o modifique la directiva predeterminada.

Para modificar la directiva predeterminada:

1. Haga doble clic en la directiva **predeterminada** . Aparece un control flotante. 

2. Seleccione **Editar configuración de protección** en la parte inferior del control flotante.

3. Después de modificar la directiva predeterminada, seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Directiva de vínculos seguros para todos los destinatarios del dominio|
|Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes.|Seleccione **Activado: las direcciones URL se volverán a escribir y comprobarán en una lista de vínculos malintencionados conocidos cuando el usuario haga clic en el vínculo**.|
|Usar Archivos adjuntos seguros para analizar el contenido descargable|Seleccione este cuadro.|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

Para obtener más información, vea [Vínculos seguros](../../security/office-365-security/safe-links.md).

## <a name="go-to-intune-admin-center"></a>Vaya al centro de administración de Intune

1. Inicie sesión en [Azure Portal](https://portal.azure.com/).

2. Seleccione **Todos los servicios** y escriba *Intune* en el **cuadro de búsqueda**.

3. Una vez que aparezcan los resultados, seleccione el inicio junto a **Microsoft Intune** para que sea un favorito y fácil de encontrar más adelante.

Además del centro de administración, puede usar Intune para inscribir y administrar los dispositivos de su organización. Para obtener más información, vea [Funcionalidades por método de inscripción para dispositivos Windows](/intune/enrollment/enrollment-method-capab) y [Opciones de inscripción para dispositivos administrados por Intune](/intune/enrollment-options).
