---
title: Aumentar la protección contra amenazas Microsoft 365 para empresas
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
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
description: Configure Microsoft Defender para Office 365 proteger los datos confidenciales frente a la suplantación de identidad(phishing), malware y otras amenazas.
ms.openlocfilehash: a02bb4be1a998cec95ea2d906e7693a3af76e313
ms.sourcegitcommit: b71a8fdda2746f18fde2c94d188be89f9cab45f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2021
ms.locfileid: "61578200"
---
# <a name="increase-threat-protection"></a>Aumentar la protección contra amenazas

Este artículo le ayuda a aumentar la protección en su suscripción Microsoft 365 para proteger contra suplantación de identidad (phishing), malware y otras amenazas. Estas recomendaciones son apropiadas para organizaciones con una mayor necesidad de seguridad, como las oficinas de abogados y las clínicas de atención médica.

Antes de empezar, compruebe su Office 365 puntuación segura. Office 365 puntuación segura analiza la seguridad de la organización en función de las actividades regulares y la configuración de seguridad, y asigna una puntuación. Comience tomando nota de la puntuación actual. Para aumentar la puntuación, complete las acciones recomendadas en este artículo. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades para proteger el entorno que no afectan negativamente a la productividad de los usuarios.

Para obtener más información, vea [Puntuación segura de Microsoft](../../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar el nivel de protección contra malware en el correo

El Office 365 o Microsoft 365 incluye protección contra malware. Puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OA7Z?autoplay=false]

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, elija **Mostrar más**, Centros **de administración** y, a continuación, **Seguridad**.

1. Vaya a **Email & collaboration** Policies & \> **rules** \> **Threat policies**.

1. En las directivas disponibles, elija **Anti-malware**.

Para aumentar la protección contra malware en el correo electrónico:

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender,</a>vaya a Correo electrónico **&** directivas de colaboración & reglas de amenazas \>  \>  \> **Directivas antimalware** en la **sección** Directivas.

2. En la **página Antimalware,** haga doble clic en **Predeterminado (predeterminado).** Aparece un desplegable. 

3. Seleccione **Editar configuración de protección** en la parte inferior del control desplegable. 

4. en **Configuración de protección,** active la casilla situada junto **a Habilitar el filtro de datos adjuntos comunes.** Los tipos de archivo bloqueados se enumeran directamente debajo de este control. Asegúrese de agregar estos tipos de archivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Para agregar o eliminar tipos de archivo, seleccione **Personalizar tipos de archivo** al final de la lista.

6. Seleccione **Guardar.**

Para obtener más información, vea [Protección contra malware en EOP](../../security/office-365-security/anti-malware-protection.md).

## <a name="protect-against-ransomware"></a>Protección contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero a las víctimas pidiendo "rescate", normalmente en forma de criptodivisas como Bitcoin, a cambio de acceso a datos.

Para protegerse contra ransomware, cree una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware. (Ha agregado estas reglas en el aumento del nivel [de protección contra malware en el paso de](#raise-the-level-of-protection-against-malware-in-mail) correo). También puede advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.

Además de los archivos bloqueados en el paso anterior, es una buena práctica crear una regla para advertir a los usuarios antes de abrir Office archivos adjuntos que incluyen macros. El ransomware se puede ocultar dentro de macros, por lo que advierte a los usuarios de que no abran estos archivos de personas que no conocen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

1. En el Centro de administración de [https://admin.microsoft.com](https://admin.microsoft.com) , elija **Exchange** en Centros **de administración**.

1. En el menú de la izquierda, elija **flujo de correo**.
 
1. En la pestaña reglas, elija la flecha situada junto al símbolo más (+) y, a continuación, **elija Crear una nueva regla**.

1. En la **página nueva regla,** escriba un nombre para la regla, desplácese hasta la parte inferior y, a continuación, elija **Más opciones**.

Para crear una regla de transporte de correo:

1. Vaya al Centro de administración en <https://admin.microsoft.com> , y elija Centros de administración  \> **Exchange**.

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, seleccione Crear una nueva regla**.

4. Seleccione **Más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la tabla siguiente para la regla. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Setting|Advertir a los usuarios antes de abrir datos adjuntos Office archivos|
|---|---|
|Nombre|Regla anti ransomware: advertir a los usuarios|
|Aplique esta regla si . . .|Cualquier dato adjunto . . . extensión de archivo coincide con . . .|
|Especificar palabras o frases|Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Haga lo siguiente. . .|Notificar al destinatario con un mensaje|
|Proporcionar texto del mensaje|No abra estos tipos de archivos de personas que no conoce porque pueden contener macros con código malintencionado.|

Para más información, vea:

- [Ransomware: cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaure el OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático para correo electrónico

Los hackers que obtienen acceso al buzón de un usuario pueden robar correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin el reconocimiento del usuario. Para evitar que esto suceda, configure una regla de flujo de correo.

Para crear una regla de transporte de correo, siga estos pasos:

1. En el Centro de administración de Microsoft 365, seleccione **Centros de administración** \> **Exchange**.

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, seleccione Crear una nueva regla**.

4. Para ver todas las opciones, seleccione **Más opciones** en la parte inferior del cuadro de diálogo.

5. Aplique la configuración en la tabla siguiente. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Setting|Advertir a los usuarios antes de abrir datos adjuntos Office archivos|
|---|---|
|Nombre|Impedir el reenvío automático de correo electrónico a dominios externos|
|Aplicar esta regla si ...|El remitente . . . es externo/interno . . . Dentro de la organización|
|Agregar condición|Las propiedades del mensaje . . . incluir el tipo de mensaje . . . Reenvío automático|
|Haga lo siguiente...|Bloquear el mensaje . . . rechazar el mensaje e incluir una explicación.|
|Proporcionar texto del mensaje|El reenvío automático de correo electrónico fuera de esta organización se impide por motivos de seguridad.|

## <a name="protect-your-email-from-phishing-attacks"></a>Proteger el correo electrónico de ataques de suplantación de identidad

Si ha configurado uno o varios dominios personalizados para su entorno Office 365 o Microsoft 365, puede configurar la protección contra suplantación de identidad dirigida. La protección contra el phishing, que forma parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización de ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.

Se recomienda empezar a usar esta protección mediante la creación de una directiva para proteger a los usuarios más importantes y al dominio personalizado.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.

2. Vaya a **Correo & directivas** de colaboración & reglas de amenazas Directivas contra \>  \>  \> **suplantación** de identidad en la **sección** Directivas.

3. En la **página Anti-phishing,** seleccione **+ Crear**. Se inicia un asistente que le permite definir la directiva contra suplantación de identidad.

4. Especifique el nombre, la descripción y la configuración de la directiva como se recomienda en la tabla siguiente. Para obtener más información, vea [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../../security/office-365-security/set-up-anti-phishing-policies.md).

5. Después de revisar la configuración, elija **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Personal de la campaña más valioso y de dominio|
|Description|Asegúrese de que el personal más importante y nuestro dominio no se suplanten.|
|Agregar usuarios que proteger|Seleccione **+ Agregar una condición, El destinatario es**. Escriba nombres de usuario o escriba la dirección de correo electrónico del candidato, el jefe de campaña y otros miembros importantes del personal. Puede agregar hasta 20 direcciones internas y externas que desea proteger de la suplantación.|
|Agregar dominios que proteger|Seleccione **+ Agregar una condición, El dominio de destinatario es**. Escriba el dominio personalizado asociado con su Microsoft 365 suscripción, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía correo electrónico: elija Redirigir mensaje a otra dirección de correo electrónico y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *Alice <span> <span> @contoso.com*. Si el correo electrónico lo envía un dominio suplantado: elija **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|Aquí puede agregar su propio dominio o cualquier otro dominio de confianza.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos**, seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla situada junto al nombre del dominio, por ejemplo, *contoso. <span> <span> com*, en la lista y, a continuación, **seleccione Agregar**. Seleccione **Listo**.|

## <a name="watch-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Watch: Protect against malicious attachments and files with Caja fuerte Attachments

Las personas envían, reciben y comparten datos adjuntos con regularidad, como documentos, presentaciones, hojas de cálculo y mucho más. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados con solo mirar un mensaje de correo electrónico. Microsoft Defender para Office 365, anteriormente denominado ATP Microsoft 365, o Protección contra amenazas avanzada, incluye Caja fuerte protección de datos adjuntos, pero esta protección no está activada de forma predeterminada. Se recomienda crear una nueva regla para empezar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

1. Vaya al Centro [de administración](https://admin.microsoft.com)y seleccione **Configurar**.
1. Desplácese hacia abajo **hasta Aumentar la protección contra amenazas avanzadas.** Seleccione **Ver**, **Administrar** y, a continuación, **Datos adjuntos seguros de ATP.**
1. Seleccione la regla de datos adjuntos seguros y, a continuación, elija el **icono** Editar.
1. Seleccione **la configuración** y, a continuación, compruebe que Bloque está seleccionado.
1. Desplácese hacia abajo. Elija **Habilitar redireccionamiento** y escriba su dirección de correo electrónico o la dirección de la persona a la que desea revisar los datos adjuntos bloqueados.
1. Seleccione **aplicado a** y, a continuación, seleccione el nombre de dominio.
1. Elija los dominios adicionales que posee (como el dominio onmicrosoft.com) a los que quiera que se aplique la regla. Seleccione **agregar** y, a continuación, **Aceptar**.
1. Seleccione **Guardar**.

Se ha actualizado la regla de datos adjuntos seguros de ATP. Ahora que la protección está en su lugar, no podrá abrir un archivo malintencionado desde Outlook, OneDrive, SharePoint o Teams. Los archivos afectados tendrán escudos rojos junto a ellos. Si alguien intenta abrir un archivo bloqueado, recibirá un mensaje de advertencia.

Después de que la directiva haya estado en su lugar durante un tiempo, visite la página Informes para ver lo que se ha analizado.

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal e</a>inicie sesión con su cuenta de administrador.

2. Vaya a **Correo & directivas** de colaboración & reglas de amenazas \>  \> **Directivas** \> **antimalware** en la **sección** Directivas.

3. Seleccione **+ Crear** para crear una nueva directiva.

4. Aplique la configuración en la tabla siguiente.

5. Después de revisar la configuración, seleccione **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Bloquear los correos electrónicos actuales y futuros con malware detectado.|
|Description|Bloquear correos electrónicos y datos adjuntos actuales y futuros con malware detectado.|
|Guardar datos adjuntos respuesta de malware desconocido|Seleccione **Bloquear: bloquee los correos electrónicos y** los datos adjuntos actuales y futuros con malware detectado.|
|Redirigir datos adjuntos al detectar|Habilitar redirección (seleccione este cuadro) Escriba la cuenta de administrador o una configuración de buzón para la cuarentena.          Aplica la selección anterior si el examen de malware para datos adjuntos se encuentra en tiempo de espera o si se produce un error (selecciona este cuadro).|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

Para obtener más información, vea [Set up anti-phishing policies in Microsoft Defender for Office 365](../../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Proteger contra ataques de suplantación de identidad con Caja fuerte links

Los hackers a veces ocultan sitios web malintencionados en vínculos de correo electrónico u otros archivos. Caja fuerte Links, parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización proporcionando la comprobación con tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos Office. La protección se define a través de Caja fuerte de vínculos.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender para Office 365 , anteriormente denominado ATP Microsoft 365, o Protección contra amenazas avanzada, ayuda a proteger su empresa contra sitios malintencionados cuando las personas hacen clic en vínculos en Office aplicaciones.

1. Vaya al Centro [de administración](https://admin.microsoft.com)y seleccione **Configurar**.

1. Desplácese hacia abajo **hasta Aumentar la protección contra amenazas avanzadas.** Seleccione **Administrar** y, **a continuación, Caja fuerte Vínculos**.

1. Seleccione **Global Configuración** y, en Bloquear las siguientes direcciones **URL,** escriba la dirección URL que desea bloquear.

Se recomienda hacer lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva directiva dirigida a todos los destinatarios de su dominio.

Para configurar los Caja fuerte, siga estos pasos:

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal e</a>inicie sesión con su cuenta de administrador.

2. o a **Correo & de colaboración** Directivas & reglas de amenazas \>  \>  \> **Directivas antimalware** en la **sección** Directivas.

3. Seleccione **+ Crear** para crear una nueva directiva o modifique la directiva predeterminada.

Para modificar la directiva predeterminada:

1. Haga doble clic en la **directiva** predeterminada. Aparece un desplegable. 

2. Seleccione **Editar configuración de protección** en la parte inferior del control desplegable.

3. Después de modificar la directiva predeterminada, seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Caja fuerte de vínculos para todos los destinatarios del dominio|
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Seleccionar Activado: las direcciones URL se reescribirán y comprobarán en una lista de **vínculos malintencionados** conocidos cuando el usuario haga clic en el vínculo .|
|Usar Caja fuerte datos adjuntos para examinar el contenido descargable|Seleccione este cuadro.|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

Para obtener más información, [vea Caja fuerte Links](../../security/office-365-security/safe-links.md).

## <a name="go-to-intune-admin-center"></a>Ir al Centro de administración de Intune

1. Inicie sesión en [Azure Portal](https://portal.azure.com/).

2. Seleccione **Todos los servicios** y escriba *Intune* en el cuadro **de búsqueda**.

3. Una vez que aparezcan los resultados, seleccione el inicio junto a **Microsoft Intune** para que sea un favorito y fácil de encontrar más adelante.

Además del Centro de administración, puedes usar Intune para inscribir y administrar los dispositivos de la organización. Para obtener más información, vea [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and Enrollment options for devices managed by [Intune](/intune/enrollment-options).
