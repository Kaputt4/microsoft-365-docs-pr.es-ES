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
description: Configurar Microsoft defender para Office 365 y proteger los datos confidenciales de suplantación de identidad, malware y otras amenazas.
ms.openlocfilehash: 2f1a26b5a2c5678871502d441b6ba64c9b011e1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842264"
---
# <a name="increase-threat-protection"></a>Aumentar la protección contra amenazas

Este artículo le ayuda a aumentar la protección en su suscripción de Microsoft 365 para protegerse contra phishing, malware y otras amenazas. Estas recomendaciones son adecuadas para organizaciones con mayor necesidad de seguridad, como las oficinas de la ley y las clínicas del cuidado de la salud.

Antes de empezar, Compruebe la puntuación segura de Office 365. La puntuación segura de Office 365 analiza la seguridad de su organización en función de las actividades habituales y la configuración de seguridad y asigna una puntuación. Empiece por tomar nota del resultado actual. Para aumentar la puntuación, complete las acciones recomendadas en este artículo. El objetivo no es conseguir el resultado máximo, pero para conocer las oportunidades de protección del entorno que no afectan negativamente a la productividad de los usuarios.

Para obtener más información, consulte [calificación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar el nivel de protección contra malware en correo

El entorno de Office 365 o Microsoft 365 incluye la protección contra malware. Puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. Para aumentar la protección contra malware en el correo electrónico:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de su cuenta de administrador.

2. En el panel de navegación izquierdo del centro de seguridad y cumplimiento, en &amp; **Administración de amenazas** , elija **Policy** \> **antimalware** de directiva.

3. Haga doble clic en la directiva predeterminada para editar esta directiva de toda la compañía.

4. Seleccione **Configuración**.

5. En **filtro de tipos de datos adjuntos comunes** , seleccione **activado**. Los tipos de archivo que están bloqueados aparecen en la ventana que se encuentra justo debajo de este control. Asegúrese de agregar estos tipos de archivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Si es necesario, puede Agregar o eliminar los tipos de archivo más adelante.

6. Seleccione **Guardar.**

Para obtener más información, vea [protección contra malware en EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="protect-against-ransomware"></a>Protección contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de los archivos o el bloqueo de las pantallas del equipo. A continuación, intenta extort dinero de víctimas solicitando "Ransom", normalmente en forma de cryptocurrencies como bitcoin, en Exchange para tener acceso a los datos.

Para proteger contra ransomware, cree una o más reglas de flujo de correo para bloquear extensiones de archivo que se usan habitualmente para ransomware. (Estas reglas se agregaron en el paso [elevar el nivel de protección contra malware en el correo](#raise-the-level-of-protection-against-malware-in-mail) ). También puede advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.

Además de los archivos bloqueados en el paso anterior, se recomienda crear una regla para advertir a los usuarios antes de abrir datos adjuntos de archivos de Office que incluyan macros. Ransomware puede estar oculto dentro de las macros, así que avise a los usuarios de que no abren estos archivos a personas que no conocen.

Para crear una regla de transporte de correo:

1. Vaya al centro de administración en <https://admin.microsoft.com> y elija **centros de administración** \> **Exchange**.

2. En la categoría **flujo de correo** , seleccione **reglas**.

3. Seleccione **+** y, a continuación, seleccione **crear una nueva regla**.

4. Seleccione **más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la siguiente tabla para la regla. Use los valores predeterminados para el resto de la configuración, a menos que quiera cambiarlos.

6. Seleccione **Guardar**.

|Configuración|Advertir a los usuarios antes de abrir datos adjuntos de archivos de Office||
|---|---|---|
|Nombre|Regla antiransomware: advertir a los usuarios|
|Aplicar esta regla si. . .|Los datos adjuntos. . . coincidencias de extensión de archivo. . .|
|Especificar palabras o frases|Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, XLA, XLAM, xll, pptm, potm, PPAM, ppsm sldm|
|Haga lo siguiente. . .|Notificar al destinatario con un mensaje|
|Proporcionar el texto del mensaje|No abra estos tipos de archivos de personas que no sabe porque podrían contener macros con código malintencionado.|

Para obtener más información, vea:

- [Ransomware: Cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar su OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Detener el reenvío automático de correo electrónico

Los hackers que obtienen acceso al buzón de un usuario pueden robar correo configurando el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin la conciencia del usuario. Para evitar que esto suceda, configure una regla de flujo de correo.

Para crear una regla de transporte de correo, vea [este breve vídeo](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) o siga estos pasos:

1. En el centro de administración de Microsoft 365, seleccione **admin Centers** \> **Exchange**.

2. En la categoría **flujo de correo** , seleccione **reglas**.

3. Seleccione **+** y, a continuación, seleccione **crear una nueva regla**.

4. Para ver todas las opciones, seleccione **más opciones** en la parte inferior del cuadro de diálogo.

5. Aplique la configuración de la tabla siguiente. Use los valores predeterminados para el resto de la configuración, a menos que quiera cambiarlos.

6. Seleccione **Guardar**.

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

Para crear una directiva contra la suplantación de identidad en Microsoft defender para Office 365, vea  [este vídeo de aprendizaje corto](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)o siga los pasos que se indican a continuación:

1. Vaya a [https://protection.office.com](https://protection.office.com).

2. En el panel de navegación izquierdo del centro de seguridad y cumplimiento, en &amp; **Administración de amenazas** , elija **Directiva**.

3. En la página **Directiva** , elija **anti-phishing**.

4. En la página **contra la suplantación de identidad** , seleccione **+ crear**. Se inicia un asistente que le guía por el proceso de definición de la Directiva antiphishing.

5. Especifique el nombre, la descripción y la configuración de la Directiva tal y como se recomienda en la tabla siguiente. Para obtener más información, consulte [información sobre la Directiva contra la suplantación de identidad en Microsoft defender para Office 365 opciones](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. Una vez que haya revisado la configuración, elija **crear esta directiva** o **Guardar** , según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Dominio y personal de la campaña más valioso|
|Description|Asegúrese de que el personal más importante y nuestro dominio no se están suplantando.|
|Agregar usuarios que proteger|Seleccionar **+ Agregar condición, el destinatario es**. Escriba los nombres de usuario o escriba la dirección de correo electrónico del candidato, el administrador de campañas y otros miembros importantes del personal. Puede Agregar hasta 20 direcciones internas y externas que desee proteger de la suplantación.|
|Agregar dominios que proteger|Seleccionar **+ Agregar una condición, el dominio del destinatario es**. Escriba el dominio personalizado asociado con la suscripción de Microsoft 365, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía un correo electrónico: elija **redirigir un mensaje a otra dirección de correo electrónico** y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, *alicia <span> <span> @contoso. com*. Si el correo electrónico lo envía un dominio suplantado: elija **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|Aquí puede agregar sus propios dominios o cualquier otro dominio de confianza.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos** , seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla de verificación situada junto al nombre del dominio, por ejemplo, *contoso. <span> <span> com* , en la lista y, a continuación, seleccione **Agregar**. Seleccione **Listo**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Protección contra datos adjuntos malintencionados y archivos con datos adjuntos seguros

Los usuarios envían, reciben y comparten con regularidad datos adjuntos, como documentos, presentaciones, hojas de cálculo, etc. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados solo mirando un mensaje de correo electrónico. Microsoft defender para Office 365 incluye protección de datos adjuntos seguros, pero esta protección no está activada de forma predeterminada. Le recomendamos que cree una nueva regla para comenzar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

Para crear una directiva de datos adjuntos seguros, vea [este breve vídeo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o siga los pasos que se indican a continuación:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el panel de navegación izquierdo del centro de seguridad y cumplimiento, en &amp; **Administración de amenazas** , elija **Directiva**.

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
|Redirigir datos adjuntos en detección|Habilitar redirección (Seleccione esta casilla) escriba la cuenta de administrador o una configuración de buzón para la cuarentena.          Aplique la selección anterior si se produce un error de análisis de malware para datos adjuntos de tiempo de espera o error (Active esta casilla).|
|Aplicado a|El dominio del destinatario es. . . Seleccione su dominio.|

Para obtener más información, consulte [set up anti-phishing policies in Microsoft defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Protección contra ataques de suplantación de identidad con vínculos seguros

A veces, los hackers ocultan sitios Web malintencionados en vínculos de correo electrónico u otros archivos. Vínculos seguros, parte de Microsoft defender para Office 365, puede ayudarle a proteger su organización proporcionando una comprobación del tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos de Office. La protección se define mediante directivas de vínculos a prueba de errores.

Le recomendamos que haga lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva Directiva dirigida a todos los destinatarios de su dominio.

Para configurar vínculos seguros, vea [este vídeo de aprendizaje corto](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)o realice los pasos siguientes:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta de administrador.

2. En el panel de navegación izquierdo del centro de seguridad y cumplimiento, en &amp; **Administración de amenazas** , elija **Directiva**.

3. En la página Directiva, elija **vínculos seguros**.

Para modificar la directiva predeterminada:

1. En la página vínculos seguros, en **directivas que se aplican a toda la organización** , seleccione la directiva **predeterminada** .

2. En **configuración que se aplica al contenido excepto al correo electrónico** , seleccione **Microsoft 365 apps for Enterprise, Office para iOS y Android**.

3. Seleccione **Guardar**.

Para crear una nueva Directiva dirigida a todos los destinatarios de su dominio:

1. En la página vínculos seguros, en **directivas que se aplican a toda la organización** , seleccione **+** para crear una nueva Directiva.

2. Aplique la configuración que se muestra en la tabla siguiente.

3. Seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Directiva de vínculos seguros para todos los destinatarios del dominio|
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Seleccione **activado: las direcciones URL se rescribirán y comprobarán con una lista de vínculos malintencionados conocidos cuando el usuario haga clic en el vínculo**.|
|Usar datos adjuntos seguros para analizar contenido descargable|Seleccione esta casilla.|
|Aplicado a|El dominio del destinatario es. . . Seleccione su dominio.|

Para obtener más información, consulte [vínculos a prueba](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)de errores.

## <a name="go-to-intune-admin-center"></a>Ir al centro de administración de Intune

1. Inicie sesión en [Azure portal](https://portal.azure.com/).

2. Seleccione **todos los servicios** y escriba *Intune* en el **cuadro de búsqueda**.

3. Una vez que se muestren los resultados, seleccione Iniciar junto a **Microsoft Intune** para convertirlo en un favorito y facilitar su búsqueda más adelante.

Además del centro de administración, puede usar Intune para inscribir y administrar los dispositivos de su organización. Para obtener más información, consulte [capacidades por método de inscripción para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) y [Opciones de inscripción para dispositivos administrados por Intune](https://docs.microsoft.com/intune/enrollment-options).
