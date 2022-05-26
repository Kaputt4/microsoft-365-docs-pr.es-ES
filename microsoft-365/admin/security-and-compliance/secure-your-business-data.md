---
title: Procedimientos recomendados para proteger Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkDEFENDER
- adminvideo
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: Proteja el correo electrónico y los datos empresariales de ciberamenazas, incluidos ransomware, suplantación de identidad (phishing) y datos adjuntos malintencionados.
ms.openlocfilehash: ca159d8d2adda033b1786355c1505cb4d66b625a
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65679656"
---
# <a name="best-practices-for-securing-microsoft-365-for-business"></a>Procedimientos recomendados para proteger Microsoft 365 para empresas

Si es una organización pequeña o mediana que usa uno de los planes de negocio de Microsoft, las instrucciones de este artículo le ayudarán a reforzar la seguridad de su organización. Entre sus opciones, Microsoft 365 Empresa Premium lidera el camino, ya que ahora incluye Microsoft Defender para Empresas y otras [protecciones de seguridad](../../business-premium/get-microsoft-365-business-premium.md). Las acciones recomendadas que se incluyen aquí le ayudarán a lograr los objetivos descritos en el [Manual de campañas de ciberseguridad](https://go.microsoft.com/fwlink/p/?linkid=2015598) de la Escuela Kennedy de Harvard.

> [!TIP]
> Si necesita ayuda con los pasos de este artículo, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="watch-a-quick-overview-of-security"></a>Vea: Introducción rápida a la seguridad

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Todos los planes de Microsoft 365 ofrecen protección y seguridad de línea base con Antivirus de Defender, pero con Microsoft 365 Empresa Premium también tiene características de protección contra amenazas, protección de datos y administración de dispositivos debido a la inclusión de Microsoft Defender para Empresas.  Estas funcionalidades adicionales protegen a su organización frente a amenazas en línea y acceso no autorizado, así como le permiten administrar los datos de la empresa en sus teléfonos, tabletas y equipos.

## <a name="security-features-comparison"></a>Comparación de características de seguridad

Para obtener información sobre una de las características del plan de servicio, haga clic en el encabezado de la tabla siguiente. 

|Tarea|Microsoft 365 Empresa Estándar|Microsoft 365 Empresa Premium|
|---|---|---|
[Protección contra contraseñas perdidas o robadas](#set-up-multi-factor-authentication) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
[Proporcionar formación a los usuarios](#train-your-users) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
[Uso de cuentas de administrador dedicadas](#use-dedicated-admin-accounts)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | 
[Protección contra malware](#protect-against-malware) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(protección para correo electrónico) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(mayor protección para el correo electrónico y los dispositivos) |
[Protección contra ransomware](#protect-against-ransomware) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(protección para el correo electrónico y el almacenamiento en la nube) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(mayor protección para dispositivos, correo electrónico y almacenamiento en la nube) |
[Cifrado de correos electrónicos confidenciales](#send-encrypted-email) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
[Protección del correo electrónico frente a ataques de suplantación de identidad](#protect-sensitive-emails) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(protección contra suplantación de identidad) | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(protección contra suplantación de identidad avanzada) |
[Protección contra archivos adjuntos, archivos y direcciones URL malintencionados en archivos de correo electrónico y Office](#protect-against-malicious-attachments-files-and-urls) | | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(vínculos Caja fuerte y datos adjuntos de Caja fuerte) |
[Aumento de la protección de los dispositivos de la organización](#increase-protection-for-your-organizations-devices) | | ![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(protección de dispositivos de nivel empresarial) |

Puede configurar rápidamente la seguridad y empezar a colaborar de forma segura con las instrucciones que proporcionamos en la biblioteca [de Microsoft 365 Empresa Premium](../../business-premium/index.md). La información de business Premium se desarrolló en asociación con el equipo de Microsoft Defendering Democracy para proteger a todos los clientes de pequeñas empresas frente a las ciberamenazas lanzadas por sofisticados ciberataques y hackers.

### <a name="about-the-microsoft-365-secure-score"></a>Acerca de la puntuación segura de Microsoft 365

Es importante que antes de empezar, compruebe la [puntuación de seguridad de Microsoft 365](../../security/defender/microsoft-secure-score.md) en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. Desde un panel centralizado, puede supervisar y mejorar la seguridad de las identidades de Microsoft 365, los datos, las aplicaciones, los dispositivos y la infraestructura. Se le proporcionan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad (como ver informes) o abordar recomendaciones con una aplicación o software de terceros. Con información agregada y más visibilidad sobre un conjunto más amplio de productos y servicios de Microsoft, puede sentirse seguro de informar sobre el estado de seguridad de su organización.

![Captura de pantalla de Puntuación de seguridad de Microsoft.](../../media/secure-score.png)

## <a name="set-up-multi-factor-authentication"></a>Configurar la autenticación multifactor

Proteja contra contraseñas perdidas o robadas mediante la autenticación multifactor (MFA). Cuando se configura la autenticación multifactor, se requiere que los usuarios usen un código en su teléfono para iniciar sesión en Microsoft 365. Este paso adicional puede impedir que los hackers se haga cargo si conocen su contraseña. 

La autenticación multifactor también se denomina verificación en dos pasos. Las personas pueden agregar la verificación en 2 pasos a la mayoría de las cuentas fácilmente, por ejemplo, a sus cuentas de Google o Microsoft. A continuación se muestra cómo [agregar la verificación en dos pasos a su cuenta personal de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=2016403).

Para las empresas que usan Microsoft 365, agregue una configuración que requiera que los usuarios inicien sesión mediante la autenticación multifactor. Cuando realice este cambio, se pedirá a los usuarios que configuren su teléfono para la autenticación en dos fases la próxima vez que inicien sesión.
Para ver un vídeo de entrenamiento sobre cómo configurar MFA y cómo los usuarios completan la configuración, consulte [Configuración de MFA](set-up-multi-factor-authentication.md) y [configuración de usuarios](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

### <a name="turn-on-security-defaults"></a>Activar los valores predeterminados de seguridad

Para la mayoría de las organizaciones, los valores predeterminados de seguridad ofrecen un buen nivel de seguridad de inicio de sesión agregado. Para más información, vea [¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) Si la suscripción es nueva, es posible que los valores predeterminados de seguridad ya estén activados automáticamente.

Habilite o deshabilite los valores predeterminados de seguridad en el panel **Propiedades** de Azure Active Directory (Azure AD) en el Azure Portal.

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con credenciales de administrador global.

2. En el panel de navegación izquierdo, elija **Mostrar todo** y, en **Centros de administración**, elija **Azure Active Directory**.

3. En el **centro de administración de Azure Active Directory**, elija **Azure Active Directory** >  **Propiedades**.

4. En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.

5. Elija **Sí** para habilitar los valores predeterminados de seguridad y **No** para deshabilitar los valores predeterminados de seguridad; a continuación, elija **Guardar**.

Después de configurar la autenticación multifactor para su organización, sus usuarios deberán configurar una verificación de dos pasos en sus dispositivos. Para obtener más información, consulte [Configuración de la comprobación en dos pasos para Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

> [!Tip]
> Si necesita un control más pormenorizado de la autenticación multifactor, puede habilitar el acceso condicional con Microsoft 365 Empresa Premium. Si lo hace, se recomienda implementar las directivas equivalentes en Valores predeterminados de seguridad. Vaya aquí para obtener más información sobre [los valores predeterminados de seguridad](/microsoft-365/business-premium/m365bp-conditional-access).

Para obtener más detalles y recomendaciones, consulte [Configuración de la autenticación multifactor para los usuarios](set-up-multi-factor-authentication.md).

## <a name="train-your-users"></a>Proporcione formación a los usuarios

El [Manual de campañas de ciberseguridad](https://go.microsoft.com/fwlink/p/?linkid=2015598) de la Escuela Kennedy de Harvard proporciona una excelente guía para establecer una sólida cultura de concienciación de seguridad dentro de su organización, incluido el entrenamiento de usuarios para identificar ataques de suplantación de identidad (phishing).

Además, Microsoft recomienda que los usuarios realicen las acciones descritas en este artículo: [Proteger su cuenta y dispositivos de hackers y malware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Entre estas acciones se incluyen:

- Uso de contraseñas seguras
- Protección de dispositivos
- Habilitación de características de seguridad en equipos Windows 10 y Mac

Microsoft también recomienda que los usuarios protejan sus cuentas de correo electrónico personales mediante las acciones recomendadas en los artículos siguientes:

- [Ayuda para proteger su cuenta de correo electrónico de Outlook.com](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Protección de su cuenta de Gmail con la verificación en 2 pasos](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="use-dedicated-admin-accounts"></a>Uso de cuentas de administrador dedicadas

Las cuentas administrativas que se usan para administrar el entorno de Microsoft 365 incluyen privilegios elevados. Estos son objetivos valiosos para los piratas informáticos y los ciberataques. Use cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para un uso normal y no administrativo y solo usar su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo. Recomendaciones adicionales:

- Asegúrese de que las cuentas se agregan a [Azure Active Directory](../../admin/add-users/add-users.md).
- Asegúrese de que las cuentas de administrador también están configuradas para la autenticación multifactor.
- Antes de usar cuentas de administrador, cierre todas las aplicaciones y sesiones de explorador no relacionadas, incluidas las cuentas de correo electrónico personales.
- Después de completar las tareas de administración, asegúrese de cerrar la sesión del explorador.

## <a name="protect-against-malware"></a>Protección contra malware

El entorno de Microsoft 365 incluye protección contra malware. Puede aumentar la protección contra malware mediante:

- Usar [directivas predefinidas para Microsoft Office 365](../../../microsoft-365/security/office-365-security/preset-security-policies.md).
- Bloquear datos adjuntos con determinados tipos de archivo.
- Usar la protección antivirus o antimalware en los dispositivos, especialmente Microsoft Defender para Empresas. Incluye características como informes [de investigación automatizados](../../security/office-365-security/air-view-investigation-results.md) (AIR) y el panel de administración de amenazas y vulnerabilidades (TVM). Cuando Microsoft Defender para Empresas no es el software antivirus principal, todavía puede ejecutarlo en modo pasivo y usar la [protección y la respuesta de los puntos de conexión (EDR),](../../security/defender-endpoint/overview-endpoint-detection-response.md) especialmente en [modo de bloque](../../security/defender-endpoint/edr-in-block-mode.md), donde funciona en segundo plano para corregir artefactos malintencionados detectados por las funcionalidades de EDR y que el software del detector de virus principal ha perdido.

### <a name="block-attachments-with-certain-file-types"></a>Bloquear datos adjuntos con determinados tipos de archivo

Puede aumentar la protección contra malware bloqueando los datos adjuntos con los tipos de archivo que se usan normalmente para el malware. Para ampliar la protección contra malware en el correo electrónico, vea un [breve vídeo de entrenamiento](increase-threat-protection.md#raise-the-level-of-protection-against-malware-in-mail) o complete los pasos siguientes:

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, vaya a **Correo electrónico &** directivas de colaboración \> **& reglas** \> **Directivas** \> **de amenazas Antimalware** en la sección **Directivas**.
2. En la página **Antimalware** , haga doble clic en **Predeterminado**. Aparece un control flotante.
3. Seleccione **Editar configuración de protección** en la parte inferior del control flotante.
4. En la página siguiente, en **Configuración de protección**, active la casilla situada junto a **Habilitar el filtro de datos adjuntos comunes**. Los tipos de archivo bloqueados se enumeran directamente debajo de esta opción. Para agregar o eliminar tipos de archivo, seleccione **Personalizar tipos de archivo** al final de la lista.
5. Haga clic en **Guardar**.

Para obtener más información, vea [Protección antimalware en EOP](../../security/office-365-security/anti-malware-protection.md).

### <a name="use-antivirus-and-anti-malware-protection"></a>Uso de antivirus y protección contra malware

Antivirus de Microsoft Defender proporciona protección antivirus y antimalware sólida y está integrada en el sistema operativo Windows.

Si su organización usa Microsoft 365 Empresa Premium, obtendrá protección adicional del dispositivo que incluye:

- Protección de última generación
- Protección contra firewalls
- Filtrado de contenido web

Estas funcionalidades se incluyen en Microsoft Defender para Empresas, una oferta que comenzará a implementarse en Microsoft 365 Empresa Premium clientes a partir del 1 de marzo de 2022.

[Más información acerca de Microsoft Defender para empresas](../../security/defender-business/mdb-overview.md).

## <a name="protect-against-ransomware"></a>Protección contra ransomware

Ransomware restringe el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero de las víctimas pidiendo "rescate", normalmente en forma de criptomonedas como Bitcoin, a cambio de acceso a los datos.

Obtiene protección contra ransomware para el correo electrónico hospedado en Microsoft 365 y para los archivos almacenados en OneDrive. Si tiene Microsoft 365 Empresa Premium, obtendrá protección contra ransomware adicional para los dispositivos de su organización.

Puede protegerse contra ransomware creando una o varias reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware, o para advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico. Un buen punto de partida es crear dos reglas:

- Use OneDrive para mover archivos, de modo que siempre estén controlados y protegidos por el acceso.

- Advertir a los usuarios antes de abrir Office archivos adjuntos que incluyen macros. Ransomware puede estar oculto dentro de macros, por lo que advertiremos a los usuarios que no abran estos archivos de personas que no conocen.

- Bloquee los tipos de archivo que podrían contener ransomware u otro código malintencionado. Comenzaremos con una lista común de ejecutables (que se enumeran en la tabla siguiente). Si su organización usa cualquiera de estos tipos ejecutables y espera que se envíen por correo electrónico, agréguelos a la regla anterior (advertir a los usuarios).

Para crear una regla de transporte de correo, vea un [breve vídeo de entrenamiento](increase-threat-protection.md#protect-against-ransomware) o complete los pasos siguientes:

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

2. En la categoría **flujo de correo** , seleccione **reglas**.

3. Seleccione **+** y, a continuación, **Cree una nueva regla**.

4. Seleccione **** en la parte inferior del cuadro de diálogo para ver el conjunto completo de opciones.

5. Aplique la configuración de la tabla siguiente para cada regla. Deje el resto de la configuración en el valor predeterminado, a menos que desee cambiarlas.

6. Haga clic en **Guardar**.

| Configuración | Advertir a los usuarios antes de abrir archivos adjuntos de Office | Bloquear tipos de archivo que podrían contener ransomware u otro código malintencionado |
|:-----|:-----|:-----|
|Nombre  <br/> |Regla contra ransomware: advertir a los usuarios  <br/> |Regla contra ransomware: tipos de archivo de bloque  <br/> |
|Aplique esta regla si es . . .  <br/> |Cualquier archivo adjunto . . . la extensión de archivo coincide con . . .  <br/> |Cualquier archivo adjunto . . . la extensión de archivo coincide con . . .  <br/> |
|Especificar palabras o frases  <br/> |Agregue estos tipos de archivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Agregue estos tipos de archivo:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Haga lo siguiente. . .  <br/> |Anteponer una declinación de responsabilidades  <br/> |Bloquee el mensaje . . . rechazar el mensaje e incluir una explicación  <br/> |
|Proporcionar texto del mensaje  <br/> |No abra estos tipos de archivos, a menos que los estuviera esperando, porque los archivos pueden contener código malintencionado y saber que el remitente no es una garantía de seguridad.  <br/> ||

> [!TIP]
> También puede agregar los archivos que desea bloquear a la lista antimalware en [Proteger contra malware](#protect-against-malware).

Para más información, vea:

- [Ransomware: cómo reducir el riesgo](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Mejor juntos: Antivirus de Microsoft Defender y Office 365](../../security/defender-endpoint/office-365-microsoft-defender-antivirus.md)

- [Restauración de la OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)


## <a name="protect-sensitive-emails"></a>Protección de correos electrónicos confidenciales

Microsoft 365 incluye Office cifrado de mensajes, que permite enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de la organización, y solo los destinatarios previstos pueden verlos. El cifrado funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico.

> [!Tip]
> Si se necesita un nivel de seguridad más estricto, su organización también debe configurar y usar el etiquetado de confidencialidad para los correos electrónicos o archivos. [Las etiquetas de confidencialidad](../../compliance/sensitivity-labels.md) permiten controlar el contenido, independientemente de dónde vaya.

### <a name="send-encrypted-email"></a>Enviar correo electrónico cifrado

Para cifrar el correo electrónico:

1. Con un nuevo correo electrónico abierto, seleccione el menú **Opciones** .
1. En la lista desplegable **Cifrar** , elija el nivel de permiso adecuado.

:::image type="content" source="../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639b.png" alt-text="Cifrado de mensajes de correo electrónico en Outlook":::

### <a name="receive-encrypted-email"></a>Recepción de correo electrónico cifrado

Si el destinatario tiene Outlook 2013 o Outlook 2016 y una cuenta de correo electrónico de Microsoft, verá una alerta sobre los permisos restringidos del elemento en el panel Lectura. Después de abrir el mensaje, el destinatario puede ver el mensaje como cualquier otro.

Si el destinatario usa otro cliente de correo electrónico o cuenta de correo electrónico, como Gmail o Yahoo, verá un vínculo que le permite iniciar sesión para leer el mensaje de correo electrónico o solicitar un código de acceso único para ver el mensaje en un explorador web. Si los usuarios no reciben el correo electrónico, deben comprobar su carpeta correo no deseado o correo no deseado.

> [!TIP]
> Para obtener más información, consulte [Enviar, ver y responder a mensajes cifrados en Outlook para PC](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="protect-the-organization"></a>Protección de la organización

Si ha configurado uno o varios dominios personalizados para el entorno de Microsoft 365, puede configurar la protección contra phishing de destino. La protección contra suplantación de identidad (phishing) se incluye en Microsoft Defender para Office 365 y puede ayudar a proteger su organización contra suplantación de identidad y otros ataques.

> [!Note]
> Si no ha configurado un dominio personalizado, no es necesario hacerlo.

Se recomienda empezar a trabajar con esta protección mediante la creación de una directiva para los usuarios más importantes y el dominio personalizado. Un buen lugar para hacerlo es en Microsoft 365 Defender, incluido con Microsoft Business Premium. Para crear una directiva contra suplantación de identidad (phishing) en Defender para Office 365, siga estos pasos:

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.

2. Vaya a **Directivas de colaboración** \> & de correo electrónico **& reglas** \> **Directivas** \> **de amenazas Anti-phishing** en la sección **Directivas** .

3. En la página Anti-phishing, seleccione **+ Crear**. Se inicia un asistente que le guiará a través de la definición de la directiva anti-phishing.

4. Especifique el nombre, la descripción y la configuración de la directiva como se recomienda en el gráfico siguiente. Para obtener más información, consulte [Información sobre la directiva contra suplantación de identidad (phishing) en Microsoft Defender para Office 365 opciones](../../security/office-365-security/set-up-anti-phishing-policies.md).

5. Después de revisar la configuración, seleccione **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Dominio y personal de campaña más valioso|
|Descripción|Asegúrese de que el personal más importante y nuestro dominio no se suplantan.|
|Agregar usuarios que proteger|Seleccione **+ Agregar una condición, El destinatario es**. Escriba los nombres de usuario o escriba la dirección de correo electrónico del candidato, el jefe de campaña y otros miembros importantes del personal. Puede agregar hasta 20 direcciones internas y externas que desea proteger contra la suplantación.|
|Agregar dominios que proteger|Seleccione **+ Agregar una condición; El dominio de destinatario es**. Escriba el dominio personalizado asociado a la suscripción de Microsoft 365, si ha definido uno. Puede escribir más de un dominio.|
|Elegir acciones|Si un usuario suplantado envía un correo electrónico: seleccione **Redirigir mensaje a otra dirección de correo electrónico** y escriba la dirección de correo electrónico del administrador de seguridad; por ejemplo, securityadmin@contoso.com. <br/> Si un dominio suplantado envía un correo electrónico: seleccione **Mensaje de cuarentena**.|
|Inteligencia de buzones|De forma predeterminada, se selecciona inteligencia de buzones al crear una directiva contra suplantación de identidad (anti-phishing). Deje esta configuración **activada** para obtener mejores resultados.|
|Agregar dominios y remitentes de confianza|En este ejemplo, no defina ninguna invalidación.|
|Aplicado a|Seleccione **El dominio del destinatario es**. En **Cualquiera de estos**, seleccione **Elegir**. Seleccione **+ Agregar**. Active la casilla situada junto al nombre del dominio, por ejemplo, contoso.com, en la lista y, a continuación, seleccione **Agregar**. Seleccione **Listo**.|

> [!TIP]
> Para obtener más información, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

## <a name="protect-against-malicious-attachments-files-and-urls"></a>Protección contra datos adjuntos, archivos y direcciones URL malintencionados

Las personas envían, reciben y comparten archivos adjuntos con regularidad, como documentos, presentaciones, hojas de cálculo, etc. No siempre es fácil saber si un archivo adjunto es seguro o malintencionado con solo mirar un mensaje de correo electrónico. Microsoft Defender para Office 365 incluye Caja fuerte protección de datos adjuntos, pero esta protección no está activada de forma predeterminada. Se recomienda crear una nueva regla para empezar a usar esta protección. Esta protección se extiende a los archivos de SharePoint, OneDrive y Microsoft Teams.

### <a name="set-up-safe-attachments"></a>Configuración de datos adjuntos de Caja fuerte

Puede usar directivas de datos adjuntos Caja fuerte preconfiguradas o crear las suyas propias. Para crear una directiva de datos adjuntos de Caja fuerte, vea un [breve vídeo de entrenamiento](increase-threat-protection.md) o complete los pasos siguientes:

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión con su cuenta de administrador.

2. Vaya a **Directivas de colaboración** \> & de correo electrónico **& reglas** \> **Directivas** \> **de amenazas Antimalware** en la sección **Directivas** .

3. Seleccione **+ Crear** para crear una nueva directiva.

4. Aplique la configuración de la tabla siguiente.

5. Después de revisar la configuración, seleccione **Crear esta directiva** o **Guardar**, según corresponda.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Bloquear correos electrónicos actuales y futuros con malware detectado.|
|Descripción|Bloquear correos electrónicos y datos adjuntos actuales y futuros con malware detectado.|
|Guardar datos adjuntos respuesta de malware desconocida|Seleccione **Bloquear: bloquee los correos electrónicos y los datos adjuntos actuales y futuros con el malware detectado**.|
|Redireccionamiento de datos adjuntos al detectar|Habilitar redireccionamiento (seleccione este cuadro) <br/> Escriba la cuenta de administrador o una configuración de buzón para la cuarentena. <br/> Aplique la selección anterior si se agota el tiempo de espera de búsqueda de datos adjuntos o se produce un error (seleccione este cuadro).|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

> [!TIP]
> Para obtener más información, consulte [Configuración de directivas contra suplantación de identidad en Defender para Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

### <a name="set-up-safe-links"></a>Configuración de vínculos de Caja fuerte

Los hackers a veces ocultan sitios web malintencionados en vínculos en el correo electrónico u otros archivos. Caja fuerte Links, que forma parte de Microsoft Defender para Office 365, puede ayudar a proteger su organización proporcionando la verificación con el tiempo de clic de las direcciones web (DIRECCIONES URL) en mensajes de correo electrónico y documentos Office. La protección se define mediante directivas de vínculos de Caja fuerte.

Haga lo siguiente para protegerse frente a ataques:

- Modifique la directiva predeterminada para aumentar la protección.

- Agregue una nueva directiva destinada a todos los destinatarios del dominio.

Para acceder a Caja fuerte Vínculos, vea un [breve vídeo de entrenamiento](increase-threat-protection.md#protect-against-phishing-attacks-with-safe-links) o complete los pasos siguientes:

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión con su cuenta de administrador.

2. Vaya a **Directivas de colaboración** \> & de correo electrónico **& reglas** \> **Directivas** \> **de amenazas Antimalware** en la sección **Directivas** .

3. Seleccione **+ Crear** para crear una nueva directiva o modifique la directiva predeterminada.

Para modificar la directiva predeterminada:

1. Haga doble clic en la directiva **predeterminada** . Aparece un control flotante. 

2. Seleccione **Editar configuración de protección** en la parte inferior del control flotante.

3. Después de modificar la directiva predeterminada, seleccione **Guardar**.

|Configuración u opción|Valor recomendado|
|---|---|
|Nombre|Caja fuerte directiva de vínculos para todos los destinatarios del dominio|
|Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes.|Seleccione **Activado: las direcciones URL se volverán a escribir y comprobarán en una lista de vínculos malintencionados conocidos cuando el usuario haga clic en el vínculo**.|
|Aplicar el examen de direcciones URL en tiempo real en busca de vínculos y vínculos sospechosos que apunten a archivos|Seleccione este cuadro.|
|Aplicado a|El dominio de destinatario es . . . seleccione el dominio.|

> [!TIP]
> Para obtener más información, consulte [vínculos de Caja fuerte en Microsoft Defender para Office 365](../../security/office-365-security/atp-safe-links.md).

## <a name="increase-protection-for-your-organizations-devices"></a>Aumento de la protección de los dispositivos de la organización

Antivirus de Microsoft Defender está integrado en el sistema operativo Windows y proporciona una buena protección contra virus y malware. Sin embargo, puede aumentar la protección de los dispositivos de su organización incorporándolos a Microsoft Defender para Empresas, que es una nueva oferta para pequeñas y medianas empresas como la suya y se incluye con [Microsoft 365 Empresa Premium](../../business-premium/index.md). Con Defender para empresas, los dispositivos de su organización están mejor protegidos contra ransomware, malware, phishing y otras amenazas.

Con Microsoft 365 Empresa Premium se obtienen características de seguridad mejoradas, como la administración de dispositivos y la protección contra amenazas avanzada. Al inscribir dispositivos en Microsoft 365 Business for Defender, los dispositivos se supervisan y protegen mediante InTune.


Para obtener más información, consulte los siguientes recursos:

- [Introducción a Microsoft Defender para Empresas](../../security/defender-business/mdb-overview.md)

- [Configuración y configuración de Microsoft Defender para Empresas](../../security/defender-business/mdb-setup-configuration.md)

- [Comenzar mediante el portal de Microsoft 365 Defender](../../security/defender-business/mdb-get-started.md)

## <a name="related-content"></a>Contenido relacionado

[Autenticación multifactor para Microsoft 365](multi-factor-authentication-microsoft-365.md) (artículo)\
[Administración y supervisión de cuentas de prioridad](/microsoft-365/security/office-365-security/configure-review-priority-account) (artículo)\
[Microsoft 365 informes en el centro de administración](../activity-reports/activity-reports.md) (vídeo)
