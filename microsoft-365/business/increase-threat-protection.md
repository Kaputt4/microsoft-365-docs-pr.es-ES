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
description: Configure Microsoft Defender para Office 365 proteger los datos confidenciales frente a la suplantación de identidad(phishing), malware y otras amenazas.
ms.openlocfilehash: 4b5142efbf4392f017cd9b96f6a9c36ef2000bb7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245152"
---
# <a name="increase-threat-protection"></a>Aumentar la protección contra amenazas

Este artículo le ayuda a aumentar la protección en su suscripción Microsoft 365 para proteger contra suplantación de identidad (phishing), malware y otras amenazas. Estas recomendaciones son apropiadas para organizaciones con una mayor necesidad de seguridad, como las oficinas de abogados y las clínicas de atención médica.

Antes de empezar, compruebe su Office 365 puntuación segura. Office 365 Puntuación segura analiza la seguridad de la organización en función de las actividades regulares y la configuración de seguridad, y asigna una puntuación. Comience tomando nota de la puntuación actual. Para aumentar la puntuación, complete las acciones recomendadas en este artículo. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades para proteger el entorno que no afectan negativamente a la productividad de los usuarios.

Para obtener más información, vea [Puntuación segura de Microsoft](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar el nivel de protección contra malware en el correo

El Office 365 o Microsoft 365 incluye protección contra malware. Puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. Para aumentar la protección contra malware en el correo electrónico:

1. Ve a [https://protection.office.com](https://protection.office.com) e inicia sesión con las credenciales de tu cuenta de administrador.

2. En el Centro de seguridad y cumplimiento, en el panel de navegación izquierdo, en Administración de &amp; amenazas, elija **Directiva**  \> **antimalware**.

3. Haga doble clic en la directiva predeterminada para editar esta directiva en toda la empresa.

4. Seleccione **Configuración**.

5. En **Filtro de tipos de datos adjuntos** comunes, seleccione **En**. Los tipos de archivo bloqueados se enumeran en la ventana directamente debajo de este control. Asegúrese de agregar estos tipos de archivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Si es necesario, puede agregar o eliminar tipos de archivo más adelante.

6. Seleccione **Guardar.**

Para obtener más información, vea [Protección contra malware en EOP](../security/office-365-security/anti-malware-protection.md).

## <a name="protect-against-ransomware"></a>Protección contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero a las víctimas pidiendo "rescate", normalmente en forma de criptodivisas como Bitcoin, a cambio de acceso a datos.

Para protegerse contra ransomware, cree una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware. (Ha agregado estas reglas en el aumento del nivel [de protección contra malware en el paso de](#raise-the-level-of-protection-against-malware-in-mail) correo). También puede advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.

Además de los archivos bloqueados en el paso anterior, es una buena práctica crear una regla para advertir a los usuarios antes de abrir Office archivos adjuntos que incluyen macros. El ransomware se puede ocultar dentro de macros, por lo que advierte a los usuarios de que no abran estos archivos de personas que no conocen.

Para crear una regla de transporte de correo:

1. Vaya al Centro de administración en <https://admin.microsoft.com> , y elija Centros de administración  \> **Exchange**.

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, seleccione Crear una nueva regla**.

4. Seleccione **Más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la tabla siguiente para la regla. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Configuración|Advertir a los usuarios antes de abrir datos adjuntos Office archivos||
|---|---|---|
|Nombre|Regla anti ransomware: advertir a los usuarios|
|Aplique esta regla si . . .|Cualquier dato adjunto . . . extensión de archivo coincide con . . .|
|Especificar palabras o frases|Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Haga lo siguiente. . .|Notificar al destinatario con un mensaje|
|Proporcionar texto del mensaje|No abra estos tipos de archivos de personas que no conoce porque pueden contener macros con código malintencionado.|

Para obtener más información, vea:

- [Ransomware: cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaure el OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático para correo electrónico

Los hackers que obtienen acceso al buzón de un usuario pueden robar correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin el reconocimiento del usuario. Para evitar que esto suceda, configure una regla de flujo de correo.

Para crear una regla de transporte de correo, vea [este breve vídeo](../business-video/stop-email-auto-forward.md) o siga estos pasos:

1. En el centro Microsoft 365 administración, seleccione **Centros de administración** \> **Exchange**.

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, seleccione Crear una nueva regla**.

4. Para ver todas las opciones, seleccione **Más opciones** en la parte inferior del cuadro de diálogo.

5. Aplique la configuración en la tabla siguiente. Use los valores predeterminados para el resto de la configuración, a menos que desee cambiarlos.

6. Seleccione **Guardar**.

|Configuración|Advertir a los usuarios antes de abrir datos adjuntos Office archivos|
|---|---|
|Nombre|Impedir el reenvío automático de correo electrónico a dominios externos|
|Aplicar esta regla si ...|El remitente . . . es externo/interno . . . Dentro de la organización|
|Agregar condición|Las propiedades del mensaje . . . incluir el tipo de mensaje . . . Reenvío automático|
|Haga lo siguiente...|Bloquear el mensaje . . . rechazar el mensaje e incluir una explicación.|
|Proporcionar texto del mensaje|El reenvío automático de correo electrónico fuera de esta organización se impide por motivos de seguridad.|


## <a name="protect-your-email-from-phishing-attacks"></a>Proteger el correo electrónico de ataques de suplantación de identidad

Si ha configurado uno o varios dominios personalizados para su entorno Office 365 o Microsoft 365, puede configurar la protección contra suplantación de identidad dirigida. La protección contra el phishing, que forma parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización de ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.

Se recomienda empezar a usar esta protección mediante la creación de una directiva para proteger a los usuarios más importantes y al dominio personalizado.

Para crear una directiva contra la suplantación de identidad en Microsoft Defender para Office 365, vea este breve [vídeo](../business-video/setup-anti-phishing.md)de aprendizaje o siga estos pasos:

1. Vaya a [https://protection.office.com](https://protection.office.com).

2. En el Centro de &amp; seguridad y cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** elija **Directiva**.

3. En la **página Directiva,** elija **Anti-phishing**.

4. En la **página Anti-phishing,** seleccione **+ Crear**. Se inicia un asistente que le permite definir la directiva contra suplantación de identidad.

5. Especifique el nombre, la descripción y la configuración de la directiva como se recomienda en la tabla siguiente. Para obtener más información, vea [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).

6. Después de revisar la configuración, elija **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Personal de la campaña más valioso y de dominio|
|Descripción|Asegúrese de que el personal más importante y nuestro dominio no se suplanten.|
|Agregar usuarios que proteger|Seleccione **+ Agregar una condición, El destinatario es**. Escriba nombres de usuario o escriba la dirección de correo electrónico del candidato, el jefe de campaña y otros miembros importantes del personal. Puede agregar hasta 20 direcciones internas y externas que desea proteger de la suplantación.|
|Agregar dominios que proteger|Seleccione **+ Agregar una condición, El dominio de destinatario es**. Escriba el dominio personalizado asociado con su Microsoft 365 suscripción, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía correo electrónico: elija Redirigir mensaje a otra dirección de correo electrónico y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *Alice <span> <span> @contoso.com*. Si el correo electrónico lo envía un dominio suplantado: elija **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|Aquí puede agregar su propio dominio o cualquier otro dominio de confianza.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos**, seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla situada junto al nombre del dominio, por ejemplo, *contoso. <span> <span> com*, en la lista y, a continuación, **seleccione Agregar**. Seleccione **Listo**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Proteger contra archivos adjuntos y archivos malintencionados con Caja fuerte adjuntos

Las personas envían, reciben y comparten datos adjuntos con regularidad, como documentos, presentaciones, hojas de cálculo y mucho más. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados con solo mirar un mensaje de correo electrónico. Microsoft Defender para Office 365 incluye Caja fuerte de datos adjuntos, pero esta protección no está activada de forma predeterminada. Se recomienda crear una nueva regla para empezar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

Para crear una directiva Caja fuerte datos adjuntos, vea [este breve vídeo](../business-video/safe-attachments.md)o complete los pasos siguientes:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el Centro de &amp; seguridad y cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** elija **Directiva**.

3. En la página Directiva, elija **Caja fuerte datos adjuntos**.

4. En la página Caja fuerte datos adjuntos, aplique esta protección de forma general activando la casilla Activar ATP para **SharePoint,** OneDrive y Microsoft Teams protección.

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

Para obtener más información, vea [Set up anti-phishing policies in Microsoft Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Proteger contra ataques de suplantación de identidad con Caja fuerte links

Los hackers a veces ocultan sitios web malintencionados en vínculos de correo electrónico u otros archivos. Caja fuerte Los vínculos, que forman parte de Microsoft Defender para Office 365, pueden ayudar a proteger su organización proporcionando la comprobación con tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos Office usuario. La protección se define a través de Caja fuerte de vínculos.

Se recomienda hacer lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva directiva dirigida a todos los destinatarios de su dominio.

Para configurar vínculos Caja fuerte, vea [este breve vídeo](../business-video/safe-links.md)de aprendizaje o siga estos pasos:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el Centro de &amp; seguridad y cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** elija **Directiva**.

3. En la página Directiva, elija **Caja fuerte Vínculos**.

Para modificar la directiva predeterminada:

1. En la página Caja fuerte, en Directivas que **se aplican a** toda la organización, seleccione la **directiva** predeterminada.

2. En **Configuración que se aplican** al contenido excepto el correo electrónico, seleccione **Aplicaciones Microsoft 365 para empresas, Office para iOS y Android**.

3. Seleccione **Guardar**.

Para crear una nueva directiva dirigida a todos los destinatarios de su dominio:

1. En la página Caja fuerte, en Directivas que se **aplican** a toda la organización, seleccione para crear una **+** nueva directiva.

2. Aplique la configuración que se muestra en la tabla siguiente.

3. Seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Caja fuerte de vínculos para todos los destinatarios del dominio|
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Seleccionar Activado: las direcciones URL se reescribirán y comprobarán en una lista de **vínculos malintencionados** conocidos cuando el usuario haga clic en el vínculo .|
|Usar Caja fuerte datos adjuntos para examinar el contenido descargable|Seleccione este cuadro.|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

Para obtener más información, [vea Caja fuerte Links](../security/office-365-security/safe-links.md).

## <a name="go-to-intune-admin-center"></a>Ir al Centro de administración de Intune

1. Inicie sesión en [Azure Portal](https://portal.azure.com/).

2. Seleccione **Todos los servicios** y escriba *Intune* en el cuadro **de búsqueda**.

3. Una vez que aparezcan los resultados, seleccione el inicio junto a **Microsoft Intune** para que sea un favorito y fácil de encontrar más adelante.

Además del Centro de administración, puedes usar Intune para inscribir y administrar los dispositivos de la organización. Para obtener más información, vea [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and Enrollment options for devices managed by [Intune](/intune/enrollment-options).
