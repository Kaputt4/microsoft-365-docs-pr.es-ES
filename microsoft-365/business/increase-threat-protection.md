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
description: Configure Microsoft Defender para Office 365 y proteja los datos confidenciales contra el phishing, malware y otras amenazas.
ms.openlocfilehash: 80ad3767b277e4808b6df4bdd977688794649e11
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050854"
---
# <a name="increase-threat-protection"></a>Aumentar la protección contra amenazas

Este artículo le ayuda a aumentar la protección de su suscripción a Microsoft 365 para protegerse contra la suplantación de identidad (phishing), malware y otras amenazas. Estas recomendaciones son apropiadas para organizaciones con una mayor necesidad de seguridad, como las oficinas de abogados y las clínicas de atención médica.

Antes de empezar, compruebe la puntuación segura de Office 365. Puntuación segura de Office 365 analiza la seguridad de la organización en función de las actividades regulares y la configuración de seguridad, y asigna una puntuación. Comience tomando nota de la puntuación actual. Para aumentar la puntuación, complete las acciones recomendadas en este artículo. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades para proteger el entorno que no afectan negativamente a la productividad de los usuarios.

Para obtener más información, vea [Puntuación segura de Microsoft](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar el nivel de protección contra malware en el correo

El entorno de Office 365 o Microsoft 365 incluye protección contra malware. Puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. Para aumentar la protección contra malware en el correo electrónico:

1. Ve a [https://protection.office.com](https://protection.office.com) e inicia sesión con las credenciales de tu cuenta de administrador.

2. En el Centro de seguridad y cumplimiento, en el panel de navegación izquierdo, en Administración de &amp; amenazas, elija **Directiva**  \> **antimalware**.

3. Haga doble clic en la directiva predeterminada para editar esta directiva en toda la empresa.

4. Seleccione **Configuración**.

5. En **Filtro de tipos de datos adjuntos** comunes, seleccione **En**. Los tipos de archivo bloqueados se enumeran en la ventana directamente debajo de este control. Asegúrese de agregar estos tipos de archivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Si es necesario, puede agregar o eliminar tipos de archivo más adelante.

6. Seleccione **Guardar.**

Para obtener más información, vea [Protección contra malware en EOP](../security/defender-365-security/anti-malware-protection.md).

## <a name="protect-against-ransomware"></a>Protección contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero a las víctimas pidiendo "rescate", normalmente en forma de criptodivisas como Bitcoin, a cambio de acceso a datos.

Para protegerse contra ransomware, cree una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware. (Ha agregado estas reglas en el aumento del nivel [de protección contra malware en el paso de](#raise-the-level-of-protection-against-malware-in-mail) correo). También puede advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.

Además de los archivos que bloqueó en el paso anterior, es una buena práctica crear una regla para advertir a los usuarios antes de abrir los datos adjuntos de archivos de Office que incluyen macros. El ransomware se puede ocultar dentro de macros, por lo que advierte a los usuarios de que no abran estos archivos de personas que no conocen.

Para crear una regla de transporte de correo:

1. Vaya al Centro de administración en <https://admin.microsoft.com> , y elija Centros de **administración** \> **Exchange**.

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, seleccione Crear una nueva regla**.

4. Seleccione **Más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la tabla siguiente para la regla. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Configuración|Advertir a los usuarios antes de abrir los datos adjuntos de los archivos de Office||
|---|---|---|
|Nombre|Regla anti ransomware: advertir a los usuarios|
|Aplique esta regla si . . .|Cualquier dato adjunto . . . extensión de archivo coincide con . . .|
|Especificar palabras o frases|Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Haga lo siguiente. . .|Notificar al destinatario con un mensaje|
|Proporcionar texto del mensaje|No abra estos tipos de archivos de personas que no conoce porque pueden contener macros con código malintencionado.|

Para más información, vea:

- [Ransomware: cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar onedrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático para correo electrónico

Los hackers que obtienen acceso al buzón de un usuario pueden robar correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin el reconocimiento del usuario. Para evitar que esto suceda, configure una regla de flujo de correo.

Para crear una regla de transporte de correo, vea [este breve vídeo](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) o siga estos pasos:

1. En el Centro de administración de Microsoft 365, seleccione **Centros de administración** \> **exchange**.

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, seleccione Crear una nueva regla**.

4. Para ver todas las opciones, seleccione **Más opciones** en la parte inferior del cuadro de diálogo.

5. Aplique la configuración en la tabla siguiente. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Configuración|Advertir a los usuarios antes de abrir los datos adjuntos de los archivos de Office|
|---|---|
|Nombre|Impedir el reenvío automático de correo electrónico a dominios externos|
|Aplicar esta regla si ...|El remitente . . . es externo/interno . . . Dentro de la organización|
|Agregar condición|Las propiedades del mensaje . . . incluir el tipo de mensaje . . . Reenvío automático|
|Haga lo siguiente...|Bloquear el mensaje . . . rechazar el mensaje e incluir una explicación.|
|Proporcionar texto del mensaje|El reenvío automático de correo electrónico fuera de esta organización se impide por motivos de seguridad.|


## <a name="protect-your-email-from-phishing-attacks"></a>Proteger el correo electrónico de ataques de suplantación de identidad

Si ha configurado uno o varios dominios personalizados para su entorno de Office 365 o Microsoft 365, puede configurar la protección contra suplantación de identidad de destino. La protección contra suplantación de identidad (phishing), que forma parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización de ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.

Se recomienda empezar a usar esta protección mediante la creación de una directiva para proteger a los usuarios más importantes y al dominio personalizado.

Para crear una directiva contra la suplantación de identidad en Microsoft Defender para Office 365, vea este breve  [vídeo](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)de aprendizaje o siga estos pasos:

1. Vaya a [https://protection.office.com](https://protection.office.com).

2. En el Centro de &amp; seguridad y cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** elija **Directiva**.

3. En la **página Directiva,** elija **Anti-phishing**.

4. En la **página Anti-phishing,** seleccione **+ Crear**. Se inicia un asistente que le permite definir la directiva contra suplantación de identidad.

5. Especifique el nombre, la descripción y la configuración de la directiva como se recomienda en la tabla siguiente. Para obtener más información, vea [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/defender-365-security/set-up-anti-phishing-policies.md).

6. Después de revisar la configuración, elija **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Personal de la campaña más valioso y de dominio|
|Descripción|Asegúrese de que el personal más importante y nuestro dominio no se suplanten.|
|Agregar usuarios que proteger|Seleccione **+ Agregar una condición, El destinatario es**. Escriba nombres de usuario o escriba la dirección de correo electrónico del candidato, el jefe de campaña y otros miembros importantes del personal. Puede agregar hasta 20 direcciones internas y externas que desea proteger de la suplantación.|
|Agregar dominios que proteger|Seleccione **+ Agregar una condición, El dominio de destinatario es**. Escriba el dominio personalizado asociado a su suscripción de Microsoft 365, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía correo electrónico: elija Redirigir mensaje a otra dirección de correo electrónico y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *Alice <span> <span> @contoso.com*. Si el correo electrónico lo envía un dominio suplantado: elija **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|Aquí puede agregar su propio dominio o cualquier otro dominio de confianza.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos**, seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla situada junto al nombre del dominio, por ejemplo, *contoso. <span> <span> com*, en la lista y, a continuación, **seleccione Agregar**. Seleccione **Listo**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Proteger contra datos adjuntos y archivos malintencionados con datos adjuntos seguros

Las personas envían, reciben y comparten datos adjuntos con regularidad, como documentos, presentaciones, hojas de cálculo y mucho más. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados con solo mirar un mensaje de correo electrónico. Microsoft Defender para Office 365 incluye protección de datos adjuntos seguros, pero esta protección no está activada de forma predeterminada. Se recomienda crear una nueva regla para empezar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

Para crear una directiva de datos adjuntos seguros, vea [este breve vídeo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o complete los pasos siguientes:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el Centro de &amp; seguridad y cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** elija **Directiva**.

3. En la página Directiva, elija **Datos adjuntos seguros**.

4. En la página Datos adjuntos seguros, aplique esta protección ampliamente activando la casilla Activar **ATP para SharePoint, OneDrive** y Microsoft Teams.

5. Seleccione **+** esta opción para crear una nueva directiva.

6. Aplique la configuración en la tabla siguiente.

7. Después de revisar la configuración, elija **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Bloquear los correos electrónicos actuales y futuros con malware detectado.|
|Descripción|Bloquear correos electrónicos y datos adjuntos actuales y futuros con malware detectado.|
|Guardar datos adjuntos respuesta de malware desconocido|Seleccione **Bloquear: bloquee los correos electrónicos y** los datos adjuntos actuales y futuros con malware detectado.|
|Redirigir datos adjuntos al detectar|Habilitar redirección (seleccione este cuadro) Escriba la cuenta de administrador o una configuración de buzón para la cuarentena.          Aplica la selección anterior si el examen de malware para datos adjuntos se encuentra en tiempo de espera o si se produce un error (selecciona este cuadro).|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

Para obtener más información, vea [Set up anti-phishing policies in Microsoft Defender for Office 365](../security/defender-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Proteger contra ataques de suplantación de identidad con vínculos seguros

Los hackers a veces ocultan sitios web malintencionados en vínculos de correo electrónico u otros archivos. Los vínculos seguros, que forman parte de Microsoft Defender para Office 365, pueden ayudar a proteger su organización proporcionando la comprobación con tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos de Office. La protección se define a través de directivas de vínculos seguros.

Se recomienda hacer lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva directiva dirigida a todos los destinatarios de su dominio.

Para configurar vínculos seguros, vea [este breve vídeo de aprendizaje](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)o siga estos pasos:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el Centro de &amp; seguridad y cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** elija **Directiva**.

3. En la página Directiva, elija **Vínculos seguros**.

Para modificar la directiva predeterminada:

1. En la página Vínculos seguros, en Directivas que se aplican a toda la **organización,** seleccione la **directiva** predeterminada.

2. En Configuración que se aplica al contenido excepto el **correo electrónico,** seleccione Aplicaciones de **Microsoft 365 para empresas, Office para iOS y Android**.

3. Seleccione **Guardar**.

Para crear una nueva directiva dirigida a todos los destinatarios de su dominio:

1. En la página Vínculos seguros, en **Directivas que se aplican** a toda la organización, seleccione para crear una nueva **+** directiva.

2. Aplique la configuración que se muestra en la tabla siguiente.

3. Seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Directiva de vínculos seguros para todos los destinatarios del dominio|
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Seleccionar Activado: las direcciones URL se reescribirán y comprobarán en una lista de **vínculos malintencionados** conocidos cuando el usuario haga clic en el vínculo .|
|Usar datos adjuntos seguros para examinar contenido descargable|Seleccione este cuadro.|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

Para obtener más información, vea [Vínculos seguros](../security/defender-365-security/safe-links.md).

## <a name="go-to-intune-admin-center"></a>Ir al Centro de administración de Intune

1. Inicie sesión en [Azure Portal](https://portal.azure.com/).

2. Seleccione **Todos los servicios** y escriba *Intune* en el cuadro **de búsqueda**.

3. Una vez que aparezcan los resultados, selecciona el inicio junto a **Microsoft Intune** para que sea un favorito y fácil de encontrar más adelante.

Además del Centro de administración, puedes usar Intune para inscribir y administrar los dispositivos de la organización. Para obtener más información, consulta [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) y Enrollment options for devices managed by [Intune](/intune/enrollment-options).
