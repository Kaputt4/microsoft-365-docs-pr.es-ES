---
title: Las 10 formas principales de proteger Microsoft 365 planes empresariales
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: Proteja el correo electrónico y los datos de su empresa frente a amenazas cibernéticas, como ransomware, phishing y datos adjuntos malintencionados.
ms.openlocfilehash: b274bb6bcdf71641ff8b196921a501bae9cbba28
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635967"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>Las 10 formas principales de proteger Microsoft 365 planes empresariales

Si es una organización pequeña o mediana que usa uno de los planes de negocio de Microsoft y su tipo de organización está dirigida por ciberdelincuentes y hackers, use las instrucciones de este artículo para aumentar la seguridad de su organización. Esta guía ayuda a su organización a lograr los objetivos descritos en el Manual de la campaña de ciberseguridad de la Escuela Kennedy [de](https://go.microsoft.com/fwlink/p/?linkid=2015598)Harvard.

Microsoft recomienda completar las tareas enumeradas en la tabla siguiente que se aplican al plan de servicio.

||Tarea|Microsoft 365 Empresa Estándar|Microsoft 365 Empresa Premium|
|---|---|---|---|
|1|[Configurar la autenticación multifactor](secure-your-business-data.md#setup)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Proporcionar formación a los usuarios](secure-your-business-data.md#train)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Usar cuentas de administrador dedicadas](secure-your-business-data.md#admin)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Aumentar el nivel de protección contra malware en el correo](secure-your-business-data.md#malware)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Protección contra ransomware](secure-your-business-data.md#ransomware)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Detener el reenvío automático para correo electrónico](secure-your-business-data.md#forwarding)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Usar Office cifrado de mensajes](secure-your-business-data.md#encryption)||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Proteger el correo electrónico de ataques de suplantación de identidad](secure-your-business-data.md#phishing)||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Proteger contra archivos adjuntos y archivos malintencionados con Caja fuerte adjuntos](secure-your-business-data.md#atp)||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Proteger contra ataques de suplantación de identidad con Caja fuerte links](secure-your-business-data.md#phishingatp)||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Si tiene Microsoft Empresa Premium, la forma más rápida de configurar la seguridad y empezar a colaborar de forma segura es seguir las instrucciones de esta biblioteca: [Microsoft 365 para empresas y campañas pequeñas](../../campaigns/index.md). Esta guía fue desarrollada en asociación con el equipo de Microsoft Defending Democracy para proteger a todos los clientes de empresas pequeñas de las amenazas cibernéticas por parte de hackers sofisticados.

Antes de empezar, compruebe su Microsoft 365 [puntuación segura](../../security/defender/microsoft-secure-score.md) en el centro Microsoft 365 seguridad. Desde un panel centralizado, puede supervisar y mejorar la seguridad de su Microsoft 365 identidades, datos, aplicaciones, dispositivos e infraestructura. Se le dan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad (como ver informes) o abordar recomendaciones con una aplicación o software de terceros. Con información adicional y más visibilidad de un conjunto más amplio de productos y servicios de Microsoft, puede tener confianza en los informes sobre el estado de seguridad de su organización.

![Captura de pantalla de Puntuación segura de Microsoft](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: Configurar la autenticación multifactor
<a name="setup"> </a>

El uso de la autenticación multifactor es una de las formas más sencillas y eficaces de aumentar la seguridad de la organización. Es más fácil de lo que parece: al iniciar sesión, la autenticación multifactor significa que escribirás un código desde el teléfono para obtener acceso a Microsoft 365. Esto puede impedir que los piratas informáticos se alopen si conocen tu contraseña. La autenticación multifactor también se denomina verificación en 2 pasos. Los individuos pueden agregar la comprobación de 2 pasos a la mayoría de las cuentas fácilmente, por ejemplo, a sus cuentas de Google o Microsoft. Este es el procedimiento para [agregar la comprobación en dos pasos a su cuenta personal de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=2016403).

Para las empresas que usan Microsoft 365, agregue una configuración que requiera que los usuarios inicien sesión con la autenticación multifactor. Al realizar este cambio, se pedirá a los usuarios que configuren su teléfono para la autenticación en dos fases la próxima vez que inicien sesión.
Para ver un vídeo de aprendizaje sobre cómo configurar MFA y cómo los usuarios completan la configuración, consulte [Configurar MFA](../../business-video/turn-on-mfa.md) y configurar [el usuario](../../business-video/set-up-mfa.md).

Para configurar la autenticación multifactor, activa los valores predeterminados de seguridad:

En la mayoría de las organizaciones, los valores predeterminados de seguridad ofrecen un buen nivel de seguridad adicional de inicio de sesión. Para obtener más información, vea [¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Si la suscripción es nueva, es posible que los valores predeterminados de seguridad ya estén activados automáticamente.

Puede habilitar o deshabilitar los valores predeterminados de seguridad en el panel **Propiedades** de Azure Active Directory (Azure AD) en Azure Portal.

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.
2. En el panel de navegación izquierdo, elija **Mostrar todo** y, en **Centros de administración**, elija **Azure Active Directory**.
3. En el **Centro de administración de Azure Active Directory** elija **Azure Active Directory** > **Propiedades**.
4. En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
5. Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad; a continuación, elija **Guardar**.

Después de configurar la autenticación multifactor para su organización, sus usuarios deberán configurar una verificación de dos pasos en sus dispositivos. Para obtener más información, vea [Set up 2-step verification for Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

Para obtener información completa y recomendaciones completas, consulte [Configurar la autenticación multifactor para los usuarios.](set-up-multi-factor-authentication.md)

## <a name="2-train-your-users"></a>2: Entrenar a los usuarios
<a name="train"> </a>

El Manual [](https://go.microsoft.com/fwlink/p/?linkid=2015598) de la campaña de ciberseguridad de la Escuela Kennedy de Harvard proporciona excelentes instrucciones para establecer una cultura sólida de concienciación de seguridad en su organización, incluida la formación de los usuarios para identificar los ataques de suplantación de identidad.

Además de esta guía, Microsoft recomienda que los usuarios tomen las acciones descritas en este artículo: Proteger su cuenta y dispositivos de [los piratas informáticos y malware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Entre estas acciones se incluyen:

- Uso de contraseñas seguras

- Protección de dispositivos

- Habilitar características de seguridad en equipos Windows 10 y Mac

Microsoft también recomienda a los usuarios proteger sus cuentas de correo electrónico personales mediante las acciones recomendadas en los siguientes artículos:

- [Ayudar a proteger su cuenta de correo Outlook.com](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Proteger tu cuenta de Gmail con la comprobación de 2 pasos](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: Usar cuentas de administrador dedicadas
<a name="admin"> </a>

Las cuentas administrativas que usa para administrar el entorno Microsoft 365 incluyen privilegios elevados. Estos son objetivos valiosos para los hackers y los ciberdelincuentes. Use cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para un uso normal y no administrativo y usar solo su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo. Recomendaciones adicionales:

- Asegúrese de que las cuentas de administración también están configuradas para la autenticación multifactor.

- Antes de usar cuentas de administrador, cierre todas las aplicaciones y sesiones de explorador no relacionadas, incluidas las cuentas de correo electrónico personales.

- Después de completar las tareas de administración, asegúrese de cerrar la sesión del explorador.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Aumentar el nivel de protección contra malware en el correo
<a name="malware"> </a>

El Microsoft 365 incluye protección contra malware, pero puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware. Para proteger contra malware en el correo electrónico, vea un [breve vídeo de aprendizaje](../../business-video/anti-malware.md)o siga estos pasos:

1. Ve a <https://protection.office.com> e inicia sesión con las credenciales de tu cuenta de administrador.

2. En el Centro de & cumplimiento, en el panel de navegación izquierdo, en **Administración** de amenazas, elija **Directiva** \> **antimalware**.

3. Haga doble clic en la directiva predeterminada para editar esta directiva en toda la empresa.

4. Seleccione **Configuración**.

5. En **Filtro de tipos de datos adjuntos** comunes, seleccione **En**. Los tipos de archivo bloqueados se enumeran en la ventana directamente debajo de este control. Puede agregar o eliminar tipos de archivo más adelante, si es necesario.

6. Seleccione **Guardar.**

Para obtener más información, vea [Protección contra malware en EOP](../../security/office-365-security/anti-malware-protection.md).

## <a name="5-protect-against-ransomware"></a>5: Proteger contra ransomware
<a name="ransomware"> </a>

Ransomware restringe el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero a las víctimas pidiendo "rescate", normalmente en forma de criptodivisas como Bitcoin, a cambio del acceso a los datos.

Puede protegerse contra ransomware creando una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware, o para advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico. Un buen punto de partida es crear dos reglas:

- Advertir a los usuarios antes de abrir Office archivos adjuntos que incluyen macros. El ransomware se puede ocultar dentro de macros, por lo que le avisaremos a los usuarios que no abran estos archivos de personas que no conocen.

- Bloquear tipos de archivo que podrían contener ransomware u otro código malintencionado. Empezaremos con una lista común de ejecutables (que se muestra en la tabla siguiente). Si su organización usa cualquiera de estos tipos ejecutables y espera que se envíen por correo electrónico, agrégrelos a la regla anterior (advierto a los usuarios).

Para crear una regla de transporte de correo, vea un [breve vídeo de aprendizaje](../../business-video/prevent-ransom-in-email.md)o siga estos pasos:

1. Vaya al [Centro de administración de Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, Cree una nueva regla**.

4. Seleccione **** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la tabla siguiente para cada regla. Deje el resto de la configuración en el valor predeterminado, a menos que desee cambiar estos valores.

6. Seleccione **Guardar**.
    
| Configuración | Advertir a los usuarios antes de abrir datos adjuntos Office archivos | Bloquear tipos de archivo que podrían contener ransomware u otro código malintencionado |
|:-----|:-----|:-----|
|Nombre  <br/> |Regla anti ransomware: advertir a los usuarios  <br/> |Regla anti ransomware: bloquear tipos de archivo  <br/> |
|Aplique esta regla si . . .  <br/> |Cualquier dato adjunto . . . extensión de archivo coincide con . . .  <br/> |Cualquier dato adjunto . . . extensión de archivo coincide con . . .  <br/> |
|Especificar palabras o frases  <br/> |Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Agregue estos tipos de archivo:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsf, wsh, exe, pif  <br/> |
|Haga lo siguiente. . .  <br/> |Anteponer un aviso de declinación de responsabilidades  <br/> |Bloquear el mensaje . . . rechazar el mensaje e incluir una explicación  <br/> |
|Proporcionar texto del mensaje  <br/> |No abra estos tipos de archivos,a menos que los esperara, porque los archivos pueden contener código malintencionado y saber que el remitente no es una garantía de seguridad.  <br/> ||
   
> [!TIP]
> También puede agregar los archivos que desea bloquear a la lista Antimalware en el [paso 4](#4-raise-the-level-of-protection-against-malware-in-mail).

Para más información vea:

- [Ransomware: cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaure el OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: Detener el reenvío automático de correo electrónico
<a name="forwarding"> </a>

Los hackers que obtienen acceso al buzón de un usuario pueden filtrar el correo configurando el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin el reconocimiento del usuario. Puede evitar que esto suceda configurando una regla de flujo de correo.

Para crear una regla de transporte de correo:

1. Vaya al [Centro de administración de Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. En la **categoría flujo de** correo, seleccione **reglas**.

3. Seleccione **+** y, **a continuación, Cree una nueva regla**.

4. Seleccione **Más opciones** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración en la tabla siguiente. Deje el resto de la configuración en el valor predeterminado, a menos que desee cambiar estos valores.

6. Seleccione **Guardar**.

|Configuración|Rechazar mensajes de correo electrónico de reenvío automático a dominios externos|
|---|---|
|Nombre|Impedir el reenvío automático de correo electrónico a dominios externos|
|Aplicar esta regla si ...|El remitente . . . es externo/interno . . . Dentro de la organización|
|Agregar condición|El destinatario . . . es externo/interno . . . Fuera de la organización|
|Agregar condición|Las propiedades del mensaje . . . incluir el tipo de mensaje . . . Reenvío automático|
|Haga lo siguiente...|Bloquear el mensaje . . . rechazar el mensaje e incluir una explicación.|
|Proporcionar texto del mensaje|El reenvío automático de correo electrónico fuera de esta organización se impide por motivos de seguridad.|

## <a name="7-use-office-message-encryption"></a>7: Usar Office cifrado de mensajes
<a name="encryption"> </a>

Office El cifrado de mensajes se incluye Microsoft 365. Ya está configurado. Con Office cifrado de mensajes, la organización puede enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de la organización. El Cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

Office Cifrado de mensajes proporciona dos opciones de protección al enviar correo:

- No reenviar

- Cifrar

Es posible que la organización haya configurado opciones adicionales que aplican una etiqueta al correo electrónico, como Confidencial.

### <a name="to-send-protected-email"></a>Para enviar correo electrónico protegido

En Outlook para PC, seleccione **Opciones** en el correo electrónico y, a continuación, elija **Permisos**.

![Cifrado de mensajes de correo electrónico en Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

En Outlook.com, seleccione **Proteger** en el correo electrónico. La protección predeterminada es **No reenviar**. Para cambiar esto para cifrar, seleccione **Cambiar permisos** \> **Cifrar**.

![Cifrado de mensajes de correo electrónico en Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>Para recibir correo electrónico cifrado

Si el destinatario tiene Outlook 2013 o Outlook 2016 y una cuenta de correo electrónico de Microsoft, verán una alerta sobre los permisos restringidos del elemento en el panel Lectura. Después de abrir el mensaje, el destinatario puede ver el mensaje como cualquier otro.

Si el destinatario usa otro cliente de correo electrónico o cuenta de correo electrónico, como Gmail o Yahoo, verá un vínculo que le permite iniciar sesión para leer el mensaje de correo electrónico o solicitar un código de acceso único para ver el mensaje en un explorador web. Si los usuarios no reciben el correo electrónico, haga que comprueben su carpeta Correo no deseado o no deseado.

Para obtener más información, vea [Enviar, ver y](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)responder a mensajes cifrados en Outlook para PC .

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Proteger el correo electrónico de ataques de suplantación de identidad
<a name="phishing"> </a>

Si ha configurado uno o varios dominios personalizados para su entorno Microsoft 365, puede configurar la protección contra suplantación de identidad dirigida. La protección contra la suplantación de identidad (phishing), una parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización de ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.

Se recomienda empezar a usar esta protección mediante la creación de una directiva para proteger a los usuarios más importantes y al dominio personalizado.

![Crear una directiva contra la suplantación de identidad en Microsoft Defender para Office 365](../../media/security-and-compliance-center.png)

Para crear una directiva contra la suplantación de identidad en Defender para Office 365, vea un breve [vídeo](../../business-video/setup-anti-phishing.md)de aprendizaje o siga estos pasos:

1. Vaya a <https://protection.office.com>.

2. En el Centro de & cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** seleccione **Directiva**.

3. En la página Directiva, seleccione **Anti-phishing**.

4. En la página Anti-phishing, seleccione **+ Crear**. Se inicia un asistente que le permite definir la directiva contra suplantación de identidad.

5. Especifique el nombre, la descripción y la configuración de la directiva como se recomienda en el siguiente gráfico. Consulta [Más información sobre la directiva contra la suplantación](../../security/office-365-security/set-up-anti-phishing-policies.md) de identidad en Microsoft Defender para obtener Office 365 opciones para obtener más información.

6. Después de revisar la configuración, seleccione **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Personal de la campaña más valioso y de dominio|
|Descripción|Asegúrese de que el personal más importante y nuestro dominio no se suplanten.|
|Agregar usuarios que proteger|Seleccione **+ Agregar una condición, El destinatario es**. Escriba nombres de usuario o escriba la dirección de correo electrónico del candidato, el jefe de campaña y otros miembros importantes del personal. Puede agregar hasta 20 direcciones internas y externas que desea proteger de la suplantación.|
|Agregar dominios que proteger|Seleccione **+ Agregar una condición, El dominio de destinatario es**. Escriba el dominio personalizado asociado con su Microsoft 365 suscripción, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía correo electrónico: seleccione Redirigir mensaje a otra dirección de correo electrónico y, a continuación, escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, securityadmin@contoso.com. <br/> Si un dominio suplantado envía correo electrónico: seleccione **Mensaje en cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|En este ejemplo, no defina ninguna invalidación.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos**, seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla situada junto al nombre del dominio, por ejemplo, contoso.com, en la lista y, a continuación, **seleccione Agregar**. Seleccione **Listo**.|
|

Para obtener más información, vea [Set up anti-phishing policies in Defender for Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: Proteger contra archivos adjuntos y archivos malintencionados con Caja fuerte adjuntos
<a name="atp"> </a>

Las personas envían, reciben y comparten datos adjuntos con regularidad, como documentos, presentaciones, hojas de cálculo y mucho más. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados con solo mirar un mensaje de correo electrónico. Microsoft Defender para Office 365 incluye Caja fuerte de datos adjuntos, pero esta protección no está activada de forma predeterminada. Se recomienda crear una nueva regla para empezar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

Para crear una directiva Caja fuerte datos adjuntos, vea un [breve vídeo de aprendizaje](../../business-video/safe-attachments.md)o siga estos pasos:

1. Ve a <https://protection.office.com> e inicia sesión con tu cuenta de administrador.

2. En el Centro de & cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** seleccione **Directiva**.

3. En la página Directiva, seleccione **Caja fuerte datos adjuntos**.

4. En la página Caja fuerte datos adjuntos, aplique esta protección de forma general activando la casilla Activar ATP para **SharePoint,** OneDrive y Microsoft Teams protección.

5. Seleccione **+** esta opción para crear una nueva directiva.

6. Aplique la configuración en la tabla siguiente.

7. Después de revisar la configuración, seleccione **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Bloquear los correos electrónicos actuales y futuros con malware detectado.|
|Descripción|Bloquear correos electrónicos y datos adjuntos actuales y futuros con malware detectado.|
|Guardar datos adjuntos respuesta de malware desconocido|Seleccione **Bloquear: bloquee los correos electrónicos y** los datos adjuntos actuales y futuros con malware detectado.|
|Redirigir datos adjuntos al detectar|Habilitar redirección (seleccione este cuadro) <br/> Escriba la cuenta de administrador o una configuración de buzón para la cuarentena. <br/> Aplica la selección anterior si el examen de malware para datos adjuntos se encuentra en tiempo de espera o si se produce un error (selecciona este cuadro).|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|
|

Para obtener más información, vea [Set up anti-phishing policies in Defender for Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: Proteger contra ataques de suplantación de identidad con Caja fuerte web
<a name="phishingatp"> </a>

Los hackers a veces ocultan sitios web malintencionados en vínculos de correo electrónico u otros archivos. Caja fuerte Los vínculos, que forman parte de Microsoft Defender para Office 365, pueden ayudar a proteger su organización proporcionando la comprobación con tiempo de clic de direcciones web (URL) en mensajes de correo electrónico y documentos Office usuario. La protección se define a través de Caja fuerte de vínculos.

Se recomienda hacer lo siguiente:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva directiva dirigida a todos los destinatarios de su dominio.

Para obtener acceso Caja fuerte, vea un [breve vídeo de aprendizaje](../../business-video/safe-links.md)o siga estos pasos:

1. Ve a <https://protection.office.com> e inicia sesión con tu cuenta de administrador.

2. En el Centro de & cumplimiento, en el panel de navegación izquierdo, en **Administración de amenazas,** seleccione **Directiva**.

3. En la página Directiva, seleccione **Caja fuerte vínculos**.

Para modificar la directiva predeterminada:

1. En la página Caja fuerte, en Directivas que se **aplican a** toda la organización, haga doble clic en la **directiva** predeterminada.

2. En **Configuración que se aplican** al contenido de Office 365 , escriba una dirección URL que se va a bloquear, como _example.com_ y seleccione **+** .

3. En **Configuración** que se aplican al contenido excepto el correo electrónico , seleccione Office 365 **aplicaciones**, No realizar un seguimiento cuando los usuarios hacen clic en vínculos seguros y No permitir que los usuarios hagan clic a través de vínculos seguros **a** la dirección **URL original.**

4. Seleccione **Guardar**.

Para crear una nueva directiva dirigida a todos los destinatarios de su dominio:

1. En la página Caja fuerte, en Directivas que se aplican a destinatarios **específicos,** seleccione **+** para crear una nueva directiva.

2. Aplique la configuración que se muestra en la tabla siguiente.

3. Seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Caja fuerte de vínculos para todos los destinatarios del dominio|
|Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes|Seleccionar Activado: las direcciones URL se reescribirán y comprobarán en una lista de **vínculos malintencionados** conocidos cuando el usuario haga clic en el vínculo .|
|Aplicar análisis de url en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos|Seleccione este cuadro.|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|
|

Para obtener más información, [vea Caja fuerte Links in Microsoft Defender for Office 365](../../security/office-365-security/atp-safe-links.md).

## <a name="related-content"></a>Contenido relacionado

[Autenticación multifactor para Microsoft 365](multi-factor-authentication-microsoft-365.md) (artículo)\
[Administrar y supervisar cuentas de prioridad](../setup/priority-accounts.md) (artículo)\
[Microsoft 365 informes en el Centro de administración](../activity-reports/activity-reports.md) (vídeo)