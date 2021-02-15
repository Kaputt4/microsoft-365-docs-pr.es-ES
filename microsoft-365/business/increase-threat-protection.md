---
title: Aumentar la protección contra amenazas para Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configure Microsoft Defender para Office 365 y proteja los datos confidenciales contra la suplantación de identidad( phishing), malware y otras amenazas.
ms.openlocfilehash: 2f1a26b5a2c5678871502d441b6ba64c9b011e1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842264"
---
# <a name="increase-threat-protection"></a>Aumentar la protección contra amenazas

Este artículo le ayuda a aumentar la protección de su suscripción de Microsoft 365 para protegerse contra suplantación de identidad( phishing), malware y otras amenazas. Estas recomendaciones son adecuadas para las organizaciones con una mayor necesidad de seguridad, como oficinas de abogados y centros de salud.

Antes de empezar, compruebe la puntuación de seguridad de Office 365. La puntuación de seguridad de Office 365 analiza la seguridad de su organización en función de sus actividades habituales y la configuración de seguridad, y asigna una puntuación. Empiece por tomar nota de la puntuación actual. Para aumentar la puntuación, complete las acciones recomendadas en este artículo. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades para proteger su entorno que no afectan negativamente a la productividad de los usuarios.

Para obtener más información, vea [Puntuación de seguridad de Microsoft.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar el nivel de protección contra malware en el correo

El entorno de Office 365 o Microsoft 365 incluye protección contra malware. Puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. Para aumentar la protección contra malware en el correo electrónico:

1. Vaya e [https://protection.office.com](https://protection.office.com) inicie sesión con las credenciales de su cuenta de administrador.

2. En el Centro de cumplimiento de seguridad, en el panel de navegación izquierdo, en Administración de &amp; amenazas, elija **Directiva**  \> **antimalware.**

3. Haga doble clic en la directiva predeterminada para editar esta directiva en toda la empresa.

4. Seleccione **Configuración**.

5. En **Filtro de tipos comunes de datos adjuntos,** seleccione **Activar**. Los tipos de archivo bloqueados se muestran en la ventana justo debajo de este control. Asegúrese de agregar estos tipos de archivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Si es necesario, puede agregar o eliminar tipos de archivo más adelante.

6. Seleccione **Guardar.**

Para obtener más información, vea [Protección antimalware en EOP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)

## <a name="protect-against-ransomware"></a>Protección contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero a las víctimas solicitando "rescate", normalmente en forma de criptodivisas, como Crypto, a cambio de acceso a los datos.

Para protegerse contra ransomware, cree una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware. (Ha agregado estas reglas al aumentar el nivel de protección contra [malware en el paso de](#raise-the-level-of-protection-against-malware-in-mail) correo). También puede advertir a los usuarios que reciben estos datos adjuntos por correo electrónico.

Además de los archivos que bloqueó en el paso anterior, es una buena práctica crear una regla para advertir a los usuarios antes de abrir los archivos adjuntos de Office que incluyen macros. El ransomware se puede ocultar dentro de las macros, por lo que advierte a los usuarios que no abran estos archivos de personas que no conocen.

Para crear una regla de transporte de correo:

1. Vaya al centro de administración en <https://admin.microsoft.com> y elija Centros de administración **de** \> **Exchange.**

2. En la **categoría de flujo de** correo, seleccione **reglas.**

3. Seleccione **+** y, a **continuación, seleccione Crear una nueva regla.**

4. Seleccione **Más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la tabla siguiente para la regla. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Setting|Advertir a los usuarios antes de abrir los datos adjuntos de los archivos de Office||
|---|---|---|
|Nombre|Regla anti ransomware: advertir a los usuarios|
|Aplique esta regla si . . .|Los datos adjuntos. . . la extensión de archivo coincide con . . .|
|Especificar palabras o frases|Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Haga lo siguiente. . .|Notificar al destinatario con un mensaje|
|Proporcionar texto del mensaje|No abra estos tipos de archivos de personas que no conoce porque pueden contener macros con código malintencionado.|

Para obtener más información, vea:

- [Ransomware: cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar onedrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático de correo electrónico

Los hackers que obtienen acceso al buzón de un usuario pueden robar correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin el conocimiento del usuario. Para evitar que esto ocurra, configure una regla de flujo de correo.

Para crear una regla de transporte de correo, vea [este breve vídeo](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) o siga estos pasos:

1. En el Centro de administración de Microsoft 365, seleccione **Centros de administración de** \> **Exchange.**

2. En la **categoría de flujo de** correo, seleccione **reglas.**

3. Seleccione **+** y, a **continuación, seleccione Crear una nueva regla.**

4. Para ver todas las opciones, seleccione **Más opciones** en la parte inferior del cuadro de diálogo.

5. Aplique la configuración de la tabla siguiente. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Setting|Advertir a los usuarios antes de abrir los datos adjuntos de los archivos de Office|
|---|---|
|Nombre|Impedir el reenvío automático de correo electrónico a dominios externos|
|Aplique esta regla si ...|El remitente . . . es externo/interno. . . Dentro de la organización|
|Agregar condición|Las propiedades del mensaje . . . incluir el tipo de mensaje . . . Reenvío automático|
|Haga lo siguiente...|Bloquear el mensaje . . . rechazar el mensaje e incluir una explicación.|
|Proporcionar texto del mensaje|El reenvío automático de correo electrónico fuera de esta organización se impide por motivos de seguridad.|


## <a name="protect-your-email-from-phishing-attacks"></a>Proteger el correo electrónico de ataques de suplantación de identidad

Si ha configurado uno o más dominios personalizados para su entorno de Office 365 o Microsoft 365, puede configurar la protección contra suplantación de identidad dirigida. La protección contra la suplantación de identidad(phishing), que forma parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización contra ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.

Se recomienda empezar a usar esta protección mediante la creación de una directiva para proteger los usuarios más importantes y el dominio personalizado.

Para crear una directiva contra suplantación de identidad en [](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)Microsoft Defender para Office 365, vea este breve vídeo de aprendizaje o siga estos pasos:

1. Vaya a [https://protection.office.com](https://protection.office.com).

2. En el Centro de cumplimiento de seguridad, en el panel de navegación izquierdo, en Administración &amp; **de amenazas,** elija **Directiva.**

3. En la **página** Directiva, elija **Anti-phishing**.

4. En la **página Contra la suplantación** de identidad, seleccione **+ Crear**. Se inicia un asistente que le permite definir la directiva contra suplantación de identidad.

5. Especifique el nombre, la descripción y la configuración de la directiva como se recomienda en la tabla siguiente. Para obtener más información, vea Más información sobre la directiva contra suplantación de identidad en [Microsoft Defender para opciones de Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

6. Después de revisar la configuración, elija **Crear esta directiva** o **Guardar,** según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Dominio y personal de campaña más valioso|
|Description|Asegúrese de que el personal más importante y nuestro dominio no se suplantan.|
|Agregar usuarios que proteger|Seleccione **+ Agregar una condición, El destinatario es**. Escriba nombres de usuario o escriba la dirección de correo electrónico del candidato, el jefe de campaña y otros miembros importantes del personal. Puede agregar hasta 20 direcciones internas y externas que desee proteger contra la suplantación.|
|Agregar dominios que proteger|Seleccione **+ Agregar una condición, el dominio del destinatario es**. Escriba el dominio personalizado asociado a su suscripción de Microsoft 365, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía correo electrónico: elija Redirigir mensaje a otra dirección de correo electrónico y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *Alicia <span> <span> @contoso.com*. Si el correo electrónico lo envía un dominio suplantado: elija **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|Aquí puede agregar su propio dominio o cualquier otro dominio de confianza.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos**, seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla junto al nombre del dominio, por ejemplo, *contoso. <span> <span> com*, en la lista y, a continuación, seleccione **Agregar**. Seleccione **Listo**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Protegerse contra archivos adjuntos malintencionados con datos adjuntos seguros

Las personas envían, reciben y comparten datos adjuntos periódicamente, como documentos, presentaciones, hojas de cálculo y mucho más. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados con solo mirar un mensaje de correo electrónico. Microsoft Defender para Office 365 incluye protección de datos adjuntos seguros, pero esta protección no está activada de forma predeterminada. Se recomienda crear una nueva regla para empezar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

Para crear una directiva de datos adjuntos seguros, vea [este breve vídeo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o siga estos pasos:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el Centro de cumplimiento de seguridad, en el panel de navegación izquierdo, en Administración &amp; **de amenazas,** elija **Directiva.**

3. En la página Directiva, elija **Datos adjuntos seguros.**

4. En la página Datos adjuntos seguros, aplique esta protección ampliamente activando la casilla Activar ATP para **SharePoint, OneDrive** y Microsoft Teams.

5. Seleccione **+** esta opción para crear una nueva directiva.

6. Aplique la configuración de la tabla siguiente.

7. Después de revisar la configuración, elija **Crear esta directiva** o **Guardar,** según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Bloquear correos electrónicos actuales y futuros con malware detectado.|
|Description|Bloquear correos electrónicos y datos adjuntos actuales y futuros con malware detectado.|
|Guardar datos adjuntos respuesta de malware desconocido|Seleccione **Bloquear: bloquee los correos electrónicos y** los datos adjuntos actuales y futuros con malware detectado.|
|Redirigir datos adjuntos al detectarse|Habilitar el redireccionamiento (seleccione este cuadro) Escriba la cuenta de administrador o una configuración de buzón para la cuarentena.          Aplica la selección anterior si se ha finalizado el análisis de malware para datos adjuntos o si se produce un error (selecciona este cuadro).|
|Aplicado a|El dominio del destinatario es . . . seleccione su dominio.|

Para obtener más información, vea [Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Protección contra ataques de suplantación de identidad con vínculos seguros

A veces, los hackers ocultan sitios web malintencionados en vínculos de correo electrónico u otros archivos. Vínculos seguros, que forma parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización proporcionando la comprobación con el tiempo de clic de las direcciones web (URL) en mensajes de correo electrónico y documentos de Office. La protección se define a través de directivas de vínculos seguros.

Le recomendamos que haga lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva directiva destinada a todos los destinatarios de su dominio.

Para configurar Vínculos seguros, vea [este breve vídeo](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)de aprendizaje o siga estos pasos:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el Centro de cumplimiento de seguridad, en el panel de navegación izquierdo, en Administración &amp; **de amenazas,** elija **Directiva.**

3. En la página Directiva, elija **Vínculos seguros.**

Para modificar la directiva predeterminada:

1. En la página Vínculos seguros, en Directivas que se aplican a toda la **organización,** seleccione la **directiva** predeterminada.

2. En Configuración que se aplica al contenido excepto al correo **electrónico,** seleccione Aplicaciones de **Microsoft 365 para empresas, Office para iOS y Android.**

3. Seleccione **Guardar**.

Para crear una nueva directiva destinada a todos los destinatarios de su dominio:

1. En la página Vínculos seguros, en **Directivas que se aplican** a toda la organización, seleccione crear una nueva **+** directiva.

2. Aplique la configuración que se muestra en la tabla siguiente.

3. Seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Directiva de vínculos seguros para todos los destinatarios del dominio|
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Seleccionar activado: las direcciones URL se reescribirán y se comprobarán con una lista de **vínculos malintencionados** conocidos cuando el usuario haga clic en el vínculo.|
|Usar datos adjuntos seguros para examinar el contenido descargable|Seleccione este cuadro.|
|Aplicado a|El dominio del destinatario es . . . seleccione su dominio.|

Para obtener más información, vea [Vínculos seguros.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)

## <a name="go-to-intune-admin-center"></a>Ir al Centro de administración de Intune

1. Inicie sesión en [Azure Portal.](https://portal.azure.com/)

2. Seleccione **Todos los servicios** y escriba *Intune* en el cuadro **de búsqueda.**

3. Una vez que aparezcan los resultados, selecciona el inicio junto a **Microsoft Intune** para que sea un favorito y fácil de encontrar más adelante.

Además del centro de administración, puedes usar Intune para inscribir y administrar los dispositivos de la organización. Para obtener más información, consulta Funcionalidades por método [de inscripción para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) y opciones de inscripción para [dispositivos administrados por Intune.](https://docs.microsoft.com/intune/enrollment-options)
