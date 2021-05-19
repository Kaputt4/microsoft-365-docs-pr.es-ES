---
title: 'Configurar su inquilino de Microsoft 365 para aumentar la seguridad '
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
description: En este tema se le guía a través de la configuración recomendada para la configuración de todo el espacio empresarial que afecta a la seguridad del Microsoft 365 empresarial.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 686768d05e37a4e103640c2973fd30abaa25630b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538944"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configurar su inquilino de Microsoft 365 para aumentar la seguridad 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este tema se le guía a través de la configuración recomendada para la configuración de todo el espacio empresarial que afecta a la seguridad del Microsoft 365 empresarial. Sus necesidades de seguridad pueden requerir más o menos seguridad. Use estas recomendaciones como punto de partida.

## <a name="check-office-365-secure-score"></a>Comprobar Office 365 puntuación segura

Office 365 Puntuación segura analiza la seguridad de la organización en función de las actividades regulares y la configuración de seguridad y asigna una puntuación. Comience tomando nota de la puntuación actual. Ajustar algunas opciones de configuración de todo el espacio empresarial aumentará la puntuación. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades para proteger el entorno que no afectan negativamente a la productividad de los usuarios. Consulta [Puntuación segura de Microsoft](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Ajustar las directivas de administración de amenazas en el centro Microsoft 365 seguridad

El Microsoft 365 seguridad incluye funcionalidades que protegen el entorno. También incluye informes y paneles que puede usar para supervisar y realizar acciones. Algunas áreas vienen con configuraciones de directiva predeterminadas. Algunas áreas no incluyen directivas o reglas predeterminadas. Visite estas directivas en administración de amenazas para ajustar la configuración de administración de amenazas para un entorno más seguro.

****

|Área|Incluye una directiva predeterminada|Recomendación|
|---|---|---|
|**Anti-phishing**|Sí|<ul><li>Protección de suplantación: si tiene Defender para Office 365 y un dominio personalizado, configure la configuración de protección de suplantación en la directiva contra suplantación predeterminada para proteger las cuentas de correo electrónico de los usuarios más valiosos, como su director general, y para proteger su dominio. Más información: [Configuración de suplantación en directivas contra suplantación de](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) identidad e Información de [suplantación](impersonation-insight.md)</li><li>Inteligencia suplantación de identidad: revise los remitentes que están suplantando su dominio. Bloquee o permita a estos remitentes. Más información: [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md) y [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</li></ul>|
|**Motor antimalware**|Sí| Edite la directiva predeterminada: <ul><li>Filtro de tipos de datos adjuntos comunes: Seleccione Activar</li></ul> <p> También puede crear directivas de filtro de malware personalizadas y aplicarlas a usuarios, grupos o dominios especificados de su organización. <p> Más información: <ul><li>[Protección contra malware](anti-malware-protection.md)</li><li>[Configurar directivas antimalware](configure-anti-malware-policies.md)</li></ul>|
|**Caja fuerte Datos adjuntos de Microsoft Defender para Office 365**|No|En la página principal de Caja fuerte datos adjuntos, haga clic en **Configuración global** y active esta configuración: <ul><li>**Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams**</li></ul> <p> Cree una directiva Caja fuerte datos adjuntos con esta configuración: <ul><li> **Bloquear:** seleccione **Bloquear como** respuesta de malware desconocida.</li><li>**Habilitar redireccionamiento:** active esta casilla y escriba una dirección de correo electrónico, como una cuenta de administrador o de cuarentena.</li><li>**Aplica la selección anterior si el examen de malware en busca** de datos adjuntos se encuentra en tiempo de espera o si se produce un error: Active esta casilla.</li><li>**_Se aplica a_*: **El dominio de destinatario es** seleccionar el \> dominio.</li></ul> <p> Más información: Caja fuerte datos adjuntos para [SharePoint, OneDrive y](mdo-for-spo-odb-and-teams.md) Microsoft Teams y Configurar directivas Caja fuerte [datos adjuntos](set-up-safe-attachments-policies.md)|
|**Caja fuerte Vínculos en Microsoft Defender para Office 365**|Sí|En la página principal de vínculos Caja fuerte, haga clic en **Configuración global:** <ul><li>**Use Caja fuerte links en: Office 365 aplicaciones**: Compruebe que esta configuración está activada.</li><li>**No realice un seguimiento cuando los usuarios hagan clic Caja fuerte vínculos:** desactive esta opción para realizar un seguimiento de los clics del usuario.</li></ul> <p> Cree una directiva Caja fuerte vínculos con esta configuración: <ul><li>**Seleccione la acción para las direcciones URL potencialmente malintencionadas** desconocidas en los mensajes: Compruebe que esta configuración está **en**.</li><li>**Seleccione la acción para las direcciones** URL desconocidas o potencialmente malintencionadas en Microsoft Teams : Compruebe que esta configuración es **On**.</li><li>**Aplicar análisis de direcciones URL en** tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos : Active esta casilla.</li><li>**Espere a que se complete el examen de direcciones URL antes de entregar el mensaje**: Active esta casilla.</li><li>**Aplicar Caja fuerte vínculos a mensajes de correo electrónico enviados dentro de la organización**: Active esta casilla</li><li>**No permitir que los usuarios hagan clic en la dirección URL original:** Active esta casilla.</li><li>**Se aplica a**: **El dominio de destinatario es** seleccionar el \> dominio.</li></ul> <p> Más información: [Configurar Caja fuerte de vínculos](set-up-safe-links-policies.md).|
|**Correo no deseado (filtrado de correo)**|Sí| Qué buscar: demasiado correo no deseado: elija la configuración personalizada y edite la directiva de filtro de correo no deseado predeterminado. Más información: Microsoft 365 protección contra correo [electrónico no deseado](anti-spam-protection.md).|
|***Autenticación de correo electrónico***|Sí|La autenticación de correo electrónico usa un sistema de nombres de dominio (DNS) para agregar información verificable a los mensajes de correo electrónico sobre el remitente de un correo electrónico. Microsoft 365 configura la autenticación de correo electrónico para su dominio predeterminado (onmicrosoft.com), pero Microsoft 365 administradores también pueden usar la autenticación de correo electrónico para dominios personalizados. Se usan tres métodos de autenticación: <ul><li>Marco de directivas de remitente (o SPF).</li><ul><li>Para el programa de instalación, vea [Configurar SPF en Microsoft 365 para ayudar a evitar la suplantación](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Consulte [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</li><li>Después de configurar DKIM, esta opción se habilita en el centro de seguridad.</li></ul><li>Autenticación de mensajes basada en dominio, informes y conformidad (DMARC).</li><ul><li>Para la configuración de DMARC [Use DMARC para validar el correo electrónico en Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Para implementaciones no estándar de SPF, implementaciones híbridas y solución de problemas: cómo Microsoft 365 usa [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)para evitar la suplantación de identidad .

## <a name="view-dashboards-and-reports-in-the-security--compliance-center"></a>Ver paneles e informes en el Centro de seguridad & cumplimiento

Visite estos informes y paneles para obtener más información sobre el estado de su entorno. Los datos de estos informes se enriquecerán a medida que su organización use Office 365 servicios. Por ahora, familiarícese con lo que puede supervisar y realizar acciones. Para obtener más información, vea [Reports in the Security & Compliance Center](../../compliance/reports-in-security-and-compliance.md).

****

|Panel|Descripción|
|---|---|
|[Panel de administración de amenazas](security-dashboard.md)|En  la sección Administración de amenazas del centro de seguridad, use este panel para ver las amenazas que ya se han manipulado y como una herramienta práctica para informar a los responsables de la toma de decisiones empresariales sobre las capacidades de investigación y respuesta de amenazas que ya han hecho para proteger su negocio.|
|[Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)|Esto también se encuentra en la **sección Administración de** amenazas del centro de seguridad. Si está investigando o experimentando un ataque contra su inquilino, use explorer (o detecciones en tiempo real) para analizar las amenazas. El Explorador (y el informe de detecciones en tiempo real) muestra el volumen de ataques con el tiempo y puede analizar estos datos por familias de amenazas, infraestructura de atacantes y mucho más. También puede marcar cualquier correo electrónico sospechoso para la lista incidentes.|
|Informes: panel|En la **sección Informes** del Centro de seguridad, vea los informes de auditoría de SharePoint online y Exchange Online organizaciones. También puede acceder a Azure Active Directory de inicio de sesión de usuario (Azure AD), los informes de actividad de usuario y el registro de auditoría de Azure AD desde la **página** Ver informes.|
|

![Panel del Centro de seguridad](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurar opciones Exchange Online configuración para todo el espacio empresarial

Muchos de los controles de seguridad y protección del centro Exchange de administración también se incluyen en el centro de seguridad. No es necesario configurar estos en ambos lugares. Estos son un par de opciones de configuración adicionales que se recomiendan.

****

|Área|Incluye una directiva predeterminada|Recomendación|
|---|---|---|
|**Correo Flow** (reglas de flujo de correo, también conocidas como reglas de transporte)|No|Agregue una regla de flujo de correo para ayudar a proteger contra ransomware bloqueando tipos de archivos ejecutables y Office tipos de archivo que contienen macros. Para obtener más información, vea [Use mail flow rules to inspect message attachments in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Vea estos temas adicionales: <ul><li>[Protección contra ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Protección contra malware y ransomware en Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Recuperarse de un ataque de ransomware en Office 365](recover-from-ransomware.md)</li></ul> <p> Cree una regla de flujo de correo para evitar el reenvío automático de correo electrónico a dominios externos. Para obtener más información, vea [Mitigating Client External Forwarding Rules with Secure Score](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score). <p> Más información: Reglas de flujo de correo (reglas de [transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Habilitar la autenticación moderna**|No|La autenticación moderna es un requisito previo para usar la autenticación multifactor (MFA). Mfa se recomienda para proteger el acceso a recursos en la nube, incluido el correo electrónico. <p> Vea estos temas: <ul><li>[Habilitar o deshabilitar la autenticación moderna en Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype Empresarial En línea: habilitar el espacio empresarial para la autenticación moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> La autenticación moderna está habilitada de forma predeterminada Office clientes de 2016, SharePoint Online y OneDrive para la Empresa. <p> Más información: [Cómo funciona la autenticación moderna para Office 2013 y Office aplicaciones cliente de 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurar directivas de uso compartido en todo el espacio empresarial SharePoint centro de administración

Recomendaciones de Microsoft para configurar SharePoint de grupo en niveles crecientes de protección, empezando por la protección de línea base. Para obtener más información, vea [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md).

SharePoint de grupo configurados en el nivel de línea base permiten compartir archivos con usuarios externos mediante vínculos de acceso anónimo. Este enfoque se recomienda en lugar de enviar archivos por correo electrónico.

Para admitir los objetivos de protección de línea base, configure directivas de uso compartido en todo el espacio empresarial como se recomienda aquí. La configuración de uso compartido de sitios individuales puede ser más restrictiva que esta directiva para todo el espacio empresarial, pero no más permisiva.

****

|Área|Incluye una directiva predeterminada|Recomendación|
|---|---|---|
|**Uso** compartido (SharePoint Online y OneDrive para la Empresa)|Sí|El uso compartido externo está habilitado de forma predeterminada. Se recomienda esta configuración: <ul><li>Permitir el uso compartido a usuarios externos autenticados y el uso de vínculos de acceso anónimo (configuración predeterminada).</li><li>Los vínculos de acceso anónimo expiran en estos días. Escriba un número, si lo desea, como 30 días.</li><li>Tipo de vínculo predeterminado: seleccione Interno (solo personas de la organización). Los usuarios que deseen compartir mediante vínculos anónimos deben elegir esta opción en el menú para compartir.</li></ul> <p> Más información: [Introducción al uso compartido externo](/sharepoint/external-sharing-overview)|
|

SharePoint centro de administración y OneDrive para la Empresa de administración incluyen la misma configuración. La configuración de cualquier centro de administración se aplica a ambos.

## <a name="configure-settings-in-azure-active-directory"></a>Configurar la configuración en Azure Active Directory

Asegúrese de visitar estas dos áreas en Azure Active Directory para completar la configuración de todo el espacio empresarial para entornos más seguros.

### <a name="configure-named-locations-under-conditional-access"></a>Configurar ubicaciones con nombre (en acceso condicional)

Si su organización incluye oficinas con acceso seguro a la red, agregue los intervalos de direcciones IP de confianza Azure Active Directory como ubicaciones con nombre. Esta característica ayuda a reducir el número de falsos positivos notificados para eventos de riesgo de inicio de sesión.

Vea: [Ubicaciones con nombre en Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicaciones que no admiten la autenticación moderna

La autenticación multifactor requiere aplicaciones compatibles con la autenticación moderna. Las aplicaciones que no admiten la autenticación moderna no se pueden bloquear mediante reglas de acceso condicional.

Para entornos seguros, asegúrese de deshabilitar la autenticación para aplicaciones que no admiten la autenticación moderna. Puede hacerlo en Azure Active Directory con un control que estará disponible próximamente.

Mientras tanto, use uno de los siguientes métodos para lograrlo para SharePoint Online y OneDrive para la Empresa:

- Use PowerShell, vea [Bloquear aplicaciones que no usan la autenticación moderna (ADAL).](/mem/intune/protect/app-modern-authentication-block)

- Configúrelo en el centro SharePoint administración en la página "Acceso de dispositivos": "Controle el acceso desde aplicaciones que no usan la autenticación moderna". Elija Bloquear.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Introducción a Cloud App Security o Office 365 Cloud App Security

Use Office 365 Cloud App Security para evaluar el riesgo, para alertar sobre actividades sospechosas y para tomar medidas automáticamente. Requiere Office 365 plan E5.

O bien, use Microsoft Cloud App Security para obtener una visibilidad más profunda incluso después de conceder acceso, controles completos y protección mejorada para todas las aplicaciones en la nube, incluidos Office 365.

Dado que esta solución recomienda el plan EMS E5, le recomendamos que empiece por Cloud App Security para que pueda usarlo con otras aplicaciones SaaS del entorno. Comience con las directivas y la configuración predeterminadas.

Más información:

- [Implementar Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)

- [Más información sobre Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [¿Qué es Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Panel de Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Recursos adicionales

Estos artículos y guías proporcionan información prescriptiva adicional para proteger el entorno Microsoft 365 usuario:

- Guía de seguridad de Microsoft para [campañas políticas,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) organizaciones sin ánimo de lucro y otras organizaciones ágiles (puede usar estas recomendaciones en cualquier entorno, especialmente en entornos solo en la nube)

- [Directivas y configuraciones de seguridad recomendadas para identidades](microsoft-365-policies-configurations.md) y dispositivos (estas recomendaciones incluyen ayuda para entornos de AD FS)