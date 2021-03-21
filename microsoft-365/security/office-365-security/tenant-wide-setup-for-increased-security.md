---
title: Configurar el inquilino de Microsoft 365 para aumentar la seguridad
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: En este tema se le guía por la configuración recomendada para la configuración de todo el espacio empresarial que afecta a la seguridad del entorno de Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 99086bbe28135a3f504986a81cfd5cff303df95c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920317"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configurar el inquilino de Microsoft 365 para aumentar la seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En este tema se le guía por la configuración recomendada para la configuración de todo el espacio empresarial que afecta a la seguridad del entorno de Microsoft 365. Sus necesidades de seguridad pueden requerir más o menos seguridad. Use estas recomendaciones como punto de partida.

## <a name="check-office-365-secure-score"></a>Comprobar puntuación segura de Office 365

Puntuación segura de Office 365 analiza la seguridad de la organización en función de las actividades regulares y la configuración de seguridad y asigna una puntuación. Comience tomando nota de la puntuación actual. Ajustar algunas opciones de configuración de todo el espacio empresarial aumentará la puntuación. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades para proteger el entorno que no afectan negativamente a la productividad de los usuarios. Consulta [Puntuación segura de Microsoft](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Ajustar las directivas de administración de amenazas en el Centro de seguridad de Microsoft 365

El Centro de seguridad de Microsoft 365 incluye funcionalidades que protegen su entorno. También incluye informes y paneles que puede usar para supervisar y realizar acciones. Algunas áreas vienen con configuraciones de directiva predeterminadas. Algunas áreas no incluyen directivas o reglas predeterminadas. Visite estas directivas en administración de amenazas para ajustar la configuración de administración de amenazas para un entorno más seguro.

****

|Área|Incluye una directiva predeterminada|Recomendación|
|---|---|---|
|**Anti-phishing**|Sí|Si tiene un dominio personalizado, configure la directiva contra suplantación de identidad predeterminada para proteger las cuentas de correo electrónico de los usuarios más valiosos, como su director general, y para proteger su dominio. <p> Revise Directivas contra la suplantación de identidad en [Office 365](set-up-anti-phishing-policies.md) y vea Configure [anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) o [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).|
|**Motor antimalware**|Sí| Edite la directiva predeterminada: <ul><li>Filtro de tipos de datos adjuntos comunes: Seleccione Activar</li></ul> <p> También puede crear directivas de filtro de malware personalizadas y aplicarlas a usuarios, grupos o dominios especificados de su organización. <p> Más información: <ul><li>[Protección contra malware](anti-malware-protection.md)</li><li>[Configurar directivas antimalware](configure-anti-malware-policies.md)</li></ul>|
|**Datos adjuntos seguros en Microsoft Defender para Office 365**|No|En la página principal de Datos adjuntos seguros, haga clic en **Configuración global** y active esta configuración: <ul><li>**Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams**</li></ul> <p> Cree una directiva de datos adjuntos seguros con esta configuración: <ul><li> **Bloquear:** seleccione **Bloquear como** respuesta de malware desconocida.</li><li>**Habilitar redireccionamiento:** active esta casilla y escriba una dirección de correo electrónico, como una cuenta de administrador o de cuarentena.</li><li>**Aplica la selección anterior si el examen de malware en busca** de datos adjuntos se encuentra en tiempo de espera o si se produce un error: Active esta casilla.</li><li>**_Se aplica a_*: **El dominio de destinatario es** seleccionar el \> dominio.</li></ul> <p> Más información: [Datos adjuntos seguros para SharePoint, OneDrive](atp-for-spo-odb-and-teams.md) y Microsoft Teams y [Configurar directivas de datos adjuntos seguros](set-up-atp-safe-attachments-policies.md)|
|**Vínculos seguros en Microsoft Defender para Office 365**|Sí|En la página principal de Vínculos seguros, haga clic **en Configuración global:** <ul><li>**Use Vínculos seguros en: Aplicaciones de Office 365:** Compruebe que esta configuración está activada.</li><li>**No realice un seguimiento cuando los usuarios hagan clic en Vínculos seguros:** desactive esta opción para realizar un seguimiento de los clics del usuario.</li></ul> <p> Cree una directiva de vínculos seguros con esta configuración: <ul><li>**Seleccione la acción para las direcciones URL potencialmente malintencionadas** desconocidas en los mensajes: Compruebe que esta configuración está **en**.</li><li>Seleccione la acción para las direcciones URL desconocidas o **potencialmente malintencionadas** de Microsoft Teams : Compruebe que esta configuración es **On**.</li><li>**Aplicar análisis de direcciones URL en** tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos : Active esta casilla.</li><li>**Espere a que se complete el examen de direcciones URL antes de entregar el mensaje**: Active esta casilla.</li><li>**Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización:** Active esta casilla</li><li>**No permitir que los usuarios hagan clic en la dirección URL original:** Active esta casilla.</li><li>**Se aplica a**: **El dominio de destinatario es** seleccionar el \> dominio.</li></ul> <p> Más información: [Configurar directivas de vínculos seguros](set-up-atp-safe-links-policies.md).|
|**Correo no deseado (filtrado de correo)**|Sí| Qué se debe tener en cuenta: <ul><li>Demasiado correo no deseado: elija la configuración personalizada y edite la directiva de filtro de correo no deseado predeterminado.</li><li>Inteligencia de suplantación: revise los remitentes que están suplantando su dominio. Bloquee o permita a estos remitentes.</li></ul> <p> Más información: Protección contra correo electrónico no deseado de [Microsoft 365](anti-spam-protection.md).|
|***Autenticación de correo electrónico***|Sí|La autenticación de correo electrónico usa un sistema de nombres de dominio (DNS) para agregar información verificable a los mensajes de correo electrónico sobre el remitente de un correo electrónico. Microsoft 365 configura la autenticación de correo electrónico para su dominio predeterminado (onmicrosoft.com), pero los administradores de Microsoft 365 también pueden usar la autenticación de correo electrónico para dominios personalizados. Se usan tres métodos de autenticación: <ul><li>Marco de directivas de remitente (o SPF).</li><ul><li>Para la instalación, vea [Configurar SPF en Microsoft 365 para ayudar a evitar la suplantación.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Consulte [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</li><li>Después de configurar DKIM, esta opción se habilita en el centro de seguridad.</li></ul><li>Autenticación de mensajes basada en dominio, informes y conformidad (DMARC).</li><ul><li>Para la configuración de DMARC [Use DMARC para validar el correo electrónico en Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Para implementaciones no estándar de SPF, implementaciones híbridas y solución de problemas: cómo [Microsoft 365 usa Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)para evitar la suplantación de identidad .

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Ver paneles e informes en los centros de seguridad y cumplimiento

Visite estos informes y paneles para obtener más información sobre el estado de su entorno. Los datos de estos informes se enriquecerán a medida que su organización use los servicios de Office 365. Por ahora, familiarícese con lo que puede supervisar y realizar acciones. Para obtener más información, vea : [Reports in the Microsoft 365 security and compliance centers](../../compliance/reports-in-security-and-compliance.md).

****

|Panel|Descripción|
|---|---|
|[Panel de administración de amenazas](security-dashboard.md)|En  la sección Administración de amenazas del centro de seguridad, use este panel para ver las amenazas que ya se han manipulado y como una herramienta práctica para informar a los responsables de la toma de decisiones empresariales sobre las capacidades de investigación y respuesta de amenazas que ya han hecho para proteger su negocio.|
|[Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)|Esto también se encuentra en la **sección Administración de** amenazas del centro de seguridad. Si está investigando o experimentando un ataque contra su inquilino, use explorer (o detecciones en tiempo real) para analizar las amenazas. El Explorador (y el informe de detecciones en tiempo real) muestra el volumen de ataques con el tiempo y puede analizar estos datos por familias de amenazas, infraestructura de atacantes y mucho más. También puede marcar cualquier correo electrónico sospechoso para la lista incidentes.|
|Informes: panel|En la **sección Informes** del Centro de seguridad, vea los informes de auditoría de las organizaciones de SharePoint Online y Exchange Online. También puede tener acceso a los informes de inicio de sesión de usuario de Azure Active Directory (Azure AD), los informes de actividad de usuario y el registro de auditoría de Azure AD desde la página Ver **informes.**|
|

![Panel del Centro de seguridad](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurar opciones adicionales para todo el espacio empresarial de Exchange Online

Muchos de los controles de seguridad y protección del Centro de administración de Exchange también se incluyen en el centro de seguridad. No es necesario configurar estos en ambos lugares. Estos son un par de opciones de configuración adicionales que se recomiendan.

****

|Área|Incluye una directiva predeterminada|Recomendación|
|---|---|---|
|**Flujo de correo** (reglas de flujo de correo, también conocidas como reglas de transporte)|No|Agregue una regla de flujo de correo para ayudar a proteger contra ransomware bloqueando los tipos de archivo ejecutables y los tipos de archivo de Office que contienen macros. Para obtener más información, vea [Use mail flow rules to inspect message attachments in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Vea estos temas adicionales: <ul><li>[Protección contra ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Protección contra malware y ransomware en Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Recuperarse de un ataque de ransomware en Office 365](recover-from-ransomware.md)</li></ul> <p> Cree una regla de flujo de correo para evitar el reenvío automático de correo electrónico a dominios externos. Para obtener más información, vea [Mitigating Client External Forwarding Rules with Secure Score](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score). <p> Más información: [Reglas de flujo de correo (reglas de transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Habilitar la autenticación moderna**|No|La autenticación moderna es un requisito previo para usar la autenticación multifactor (MFA). Mfa se recomienda para proteger el acceso a recursos en la nube, incluido el correo electrónico. <p> Vea estos temas: <ul><li>[Habilitar o deshabilitar la autenticación moderna en Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype Empresarial Online: habilitar el espacio empresarial para la autenticación moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> La autenticación moderna está habilitada de forma predeterminada para clientes de Office 2016, SharePoint Online y OneDrive para la Empresa. <p> Más información: Cómo funciona la autenticación moderna para las aplicaciones cliente de [Office 2013 y Office 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurar directivas de uso compartido para todo el espacio empresarial en el Centro de administración de SharePoint

Recomendaciones de Microsoft para configurar sitios de grupo de SharePoint en niveles crecientes de protección, empezando por la protección de línea base. Para obtener más información, vea [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md).

Los sitios de grupo de SharePoint configurados en el nivel de línea base permiten compartir archivos con usuarios externos mediante vínculos de acceso anónimo. Este enfoque se recomienda en lugar de enviar archivos por correo electrónico.

Para admitir los objetivos de protección de línea base, configure directivas de uso compartido en todo el espacio empresarial como se recomienda aquí. La configuración de uso compartido de sitios individuales puede ser más restrictiva que esta directiva para todo el espacio empresarial, pero no más permisiva.

****

|Área|Incluye una directiva predeterminada|Recomendación|
|---|---|---|
|**Uso** compartido (SharePoint Online y OneDrive para la Empresa)|Sí|El uso compartido externo está habilitado de forma predeterminada. Se recomienda esta configuración: <ul><li>Permitir el uso compartido a usuarios externos autenticados y el uso de vínculos de acceso anónimo (configuración predeterminada).</li><li>Los vínculos de acceso anónimo expiran en estos días. Escriba un número, si lo desea, como 30 días.</li><li>Tipo de vínculo predeterminado: seleccione Interno (solo personas de la organización). Los usuarios que deseen compartir mediante vínculos anónimos deben elegir esta opción en el menú para compartir.</li></ul> <p> Más información: [Introducción al uso compartido externo](/sharepoint/external-sharing-overview)|
|

El Centro de administración de SharePoint y el Centro de administración de OneDrive para la Empresa incluyen la misma configuración. La configuración de cualquier centro de administración se aplica a ambos.

## <a name="configure-settings-in-azure-active-directory"></a>Configurar la configuración en Azure Active Directory

Asegúrese de visitar estas dos áreas en Azure Active Directory para completar la configuración de todo el espacio empresarial para entornos más seguros.

### <a name="configure-named-locations-under-conditional-access"></a>Configurar ubicaciones con nombre (en acceso condicional)

Si su organización incluye oficinas con acceso seguro a la red, agregue los intervalos de direcciones IP de confianza a Azure Active Directory como ubicaciones con nombre. Esta característica ayuda a reducir el número de falsos positivos notificados para eventos de riesgo de inicio de sesión.

Vea: [Ubicaciones con nombre en Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicaciones que no admiten la autenticación moderna

La autenticación multifactor requiere aplicaciones compatibles con la autenticación moderna. Las aplicaciones que no admiten la autenticación moderna no se pueden bloquear mediante reglas de acceso condicional.

Para entornos seguros, asegúrese de deshabilitar la autenticación para aplicaciones que no admiten la autenticación moderna. Puede hacerlo en Azure Active Directory con un control que estará disponible próximamente.

Mientras tanto, use uno de los siguientes métodos para lograrlo para SharePoint Online y OneDrive para la Empresa:

- Use PowerShell, vea [Bloquear aplicaciones que no usan la autenticación moderna (ADAL).](/mem/intune/protect/app-modern-authentication-block)

- Configúrelo en el Centro de administración de SharePoint en la página "Acceso a dispositivos": "Controle el acceso desde aplicaciones que no usan la autenticación moderna". Elija Bloquear.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Introducción a Cloud App Security o Office 365 Cloud App Security

Use Office 365 Cloud App Security para evaluar el riesgo, alertar sobre actividad sospechosa y tomar medidas automáticamente. Requiere un plan de Office 365 E5.

O bien, use Microsoft Cloud App Security para obtener una visibilidad más profunda incluso después de conceder acceso, controles completos y protección mejorada para todas las aplicaciones en la nube, incluida Office 365.

Dado que esta solución recomienda el plan EMS E5, se recomienda empezar con Cloud App Security para que pueda usarlo con otras aplicaciones SaaS del entorno. Comience con las directivas y la configuración predeterminadas.

Más información:

- [Implementar Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)

- [Más información sobre Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [¿Qué es Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Panel de Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Recursos adicionales

Estos artículos y guías proporcionan información prescriptiva adicional para proteger el entorno de Microsoft 365:

- Guía de seguridad de Microsoft para [campañas políticas,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) organizaciones sin ánimo de lucro y otras organizaciones ágiles (puede usar estas recomendaciones en cualquier entorno, especialmente en entornos solo en la nube)

- [Directivas y configuraciones de seguridad recomendadas para identidades](microsoft-365-policies-configurations.md) y dispositivos (estas recomendaciones incluyen ayuda para entornos de AD FS)