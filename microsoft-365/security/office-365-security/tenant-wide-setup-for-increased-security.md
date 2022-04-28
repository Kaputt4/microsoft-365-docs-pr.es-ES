---
title: Configurar el inquilino de Microsoft 365 para aumentar la seguridad
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 04/06/2022
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
description: En este tema se describe la configuración recomendada para la configuración de todo el inquilino que afecta a la seguridad del entorno de Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 30b46bd541f233430506766eabc2d667fad52c22
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097302"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configurar el inquilino de Microsoft 365 para aumentar la seguridad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este tema se describe la configuración recomendada para la configuración de todo el inquilino que afecta a la seguridad del entorno de Microsoft 365. Es posible que las necesidades de seguridad requieran más o menos seguridad. Use estas recomendaciones como punto de partida.

## <a name="check-office-365-secure-score"></a>Comprobación de Office 365 puntuación segura

Office 365 Puntuación de seguridad analiza la seguridad de su organización en función de las actividades normales y la configuración de seguridad y asigna una puntuación. Empiece por tomar nota de la puntuación actual. Ajustar algunas opciones de configuración de todo el inquilino aumentará la puntuación. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades de proteger el entorno que no afectan negativamente a la productividad de los usuarios. Consulte [Puntuación de seguridad de Microsoft](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Ajuste de las directivas de administración de amenazas en el portal de Microsoft 365 Defender

El portal de Microsoft 365 Defender incluye funcionalidades que protegen el entorno. También incluye informes y paneles que puede usar para supervisar y tomar medidas. Algunas áreas incluyen configuraciones de directiva predeterminadas. Algunas áreas no incluyen directivas o reglas predeterminadas. Visite estas directivas en **Directivas de colaboración** \> & correo electrónico **& reglas Directivas** \> de amenazas para ajustar la configuración de administración de amenazas para un entorno más seguro.

|Área|¿Directiva predeterminada?|Recomendación|
|---|---|---|
|**Anti-phishing**|Sí|Configure la directiva de anti phishing predeterminada como se describe aquí: [Configure las opciones de protección contra suplantación de identidad en EOP y Defender para Office 365](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365). <p> Más información: <ul><li>[Directivas contra suplantación de identidad en Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Configuración recomendada de directivas contra suplantación de identidad (phishing) en Microsoft Defender para Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [Información sobre la suplantación](impersonation-insight.md)</li><li>[Información de inteligencia sobre suplantación de identidad en EOP](learn-about-spoof-intelligence.md)</li><li>[Administre la lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md).</li></ul>|
|**Motor antimalware**|Sí|Configure la directiva antimalware predeterminada como se describe aquí: [Configure anti-malware protection settings in EOP (Configuración de la protección antimalware en EOP](protect-against-threats.md#part-1---anti-malware-protection-in-eop)). <p> Más información: <ul><li>[Protección contra malware](anti-malware-protection.md)</li><li>[Configuración recomendada de directivas antimalware](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[Configurar directivas antimalware](configure-anti-malware-policies.md)</li></ul>|
|**Datos adjuntos seguros en Microsoft Defender para Office 365**|No|Configure los valores globales de Caja fuerte Attachments y cree una directiva de datos adjuntos de Caja fuerte como se describe aquí: [Configure Caja fuerte Attachments settings in Microsoft Defender para Office 365 (Configurar datos adjuntos de Caja fuerte en Microsoft Defender para Office 365](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)). <p> Más información: <ul><li>[Configuración de datos adjuntos de Caja fuerte recomendada](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[datos adjuntos de Caja fuerte en Microsoft Defender para Office 365](safe-attachments.md)</li><li>[Configurar directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md)</li><li>[Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Documentos seguros en Microsoft 365 E5](safe-docs.md)</li></ul>|
|**vínculos de Caja fuerte en Microsoft Defender para Office 365**|No|Configure los valores globales de Caja fuerte Links y cree una directiva de vínculos de Caja fuerte como se describe aquí: [Configuración de Caja fuerte Links en Microsoft Defender para Office 365](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365). <p> Más información: <ul><li>[Configuración recomendada de vínculos de Caja fuerte](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[Configurar directivas de vínculos seguros](set-up-safe-links-policies.md)</li><li>[vínculos de Caja fuerte en Microsoft Defender para Office 365](safe-links.md)</li><li>[Configuración global de los vínculos de Caja fuerte en Microsoft Defender para Office 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**Antispam (filtrado de correo)**|Sí|Configure la directiva de antispam predeterminada como se describe aquí: [Configuración de la protección contra correo no deseado en EOP](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> Más información: <ul><li>[Configuración recomendada de directivas contra correo no deseado](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[Protección contra correo no deseado en EOP](anti-spam-protection.md)</li><li>[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)</li></ul>|
|***Autenticación por correo electrónico***|Sí|La autenticación por correo electrónico usa registros DNS para agregar información verificable a los mensajes de correo electrónico sobre el origen y el remitente del mensaje. Microsoft 365 configura automáticamente la autenticación de correo electrónico para su dominio predeterminado (onmicrosoft.com), pero los administradores de Microsoft 365 también pueden configurar la autenticación por correo electrónico para dominios personalizados. Se usan tres métodos de autenticación: <ul><li>Marco de directivas de remitente (o SPF).</li><ul><li>Para obtener información sobre la configuración, consulte [Configuración de SPF en Microsoft 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</li></ul> <li>Correo identificado de DomainKeys (DKIM).</li><ul><li>Consulte [Uso de DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado](use-dkim-to-validate-outbound-email.md).</li><li>Después de configurar DKIM, habilítelo en el portal de Microsoft 365 Defender.</li></ul><li>Autenticación de mensajes basada en dominio, informes y conformidad (DMARC).</li><ul><li>Para la configuración de DMARC[, use DMARC para validar el correo electrónico en Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|

> [!NOTE]
> Para implementaciones no estándar de SPF, implementaciones híbridas y solución de problemas: [cómo Microsoft 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Visualización de paneles e informes en el portal de Microsoft 365 Defender

Visite estos informes y paneles para obtener más información sobre el estado de su entorno. Los datos de estos informes se enriquecerán a medida que la organización use Office 365 servicios. Por ahora, esté familiarizado con lo que puede supervisar y tomar medidas.

|Panel|Descripción|
|---|---|
|Informes de seguridad de correo electrónico|Estos informes están disponibles en Exchange Online Protection. Para obtener más información, vea [Ver informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender](view-email-security-reports.md).|
|informes de Defender para Office 365|Los informes solo están disponibles en Defender para Office 365. Para obtener más información, vea [Ver informes de Defender para Office 365 en el portal de Microsoft 365 Defender](view-reports-for-mdo.md).|
|Informes e información de flujo de correo|Estos informes e información están disponibles en el Centro de administración de Exchange (EAC). Para obtener más información, vea [Informes de flujo de correo](/exchange/monitoring/mail-flow-reports/mail-flow-reports) e [Información de flujo de correo](/exchange/monitoring/mail-flow-insights/mail-flow-insights).|
|[Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)|Si está investigando o experimentando un ataque contra el inquilino, use el Explorador (o las detecciones en tiempo real) para analizar las amenazas. El Explorador (y el informe de detecciones en tiempo real) muestra el volumen de ataques a lo largo del tiempo y puede analizar estos datos por familias de amenazas, infraestructura de atacantes, etc. También puede marcar cualquier correo electrónico sospechoso para la lista incidentes.|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configuración adicional de Exchange Online en todo el inquilino

Estos son un par de configuraciones adicionales que se recomiendan.

|Área|Recomendación|
|---|---|
|**Reglas de flujo de correo** (también conocidas como reglas de transporte)|Agregue una regla de flujo de correo para ayudar a proteger contra ransomware bloqueando los tipos de archivo ejecutables y Office tipos de archivo que contienen macros. Para obtener más información, consulte [Uso de reglas de flujo de correo para inspeccionar los datos adjuntos de mensajes en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Consulte estos temas adicionales: <ul><li>[Protección contra ransomware](../../admin/security-and-compliance/secure-your-business-data.md)</li><li>[Protección contra malware y ransomware en Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Recuperación de un ataque de ransomware en Office 365](recover-from-ransomware.md)</li></ul> <p> Cree una regla de flujo de correo para evitar el reenvío automático de correo electrónico a dominios externos. Para obtener más información, vea [Mitigating Client External Forwarding Rules with Secure Score (Mitigación de reglas de reenvío externo de cliente con puntuación segura).](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Más información: [Reglas de flujo de correo (reglas de transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Autenticación moderna**|La autenticación moderna es un requisito previo para usar la autenticación multifactor (MFA). Mfa se recomienda para proteger el acceso a los recursos en la nube, incluido el correo electrónico. <p> Consulte estos temas: <ul><li>[Habilitar o deshabilitar la autenticación moderna en Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype Empresarial En línea: Habilitar el inquilino para la autenticación moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> La autenticación moderna está habilitada de forma predeterminada para los clientes de Office 2016, SharePoint Online y OneDrive para la Empresa. <p> Más información: [Funcionamiento de la autenticación moderna para las aplicaciones cliente de Office 2013 y Office 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configuración de directivas de uso compartido para todo el inquilino en SharePoint centro de administración

Recomendaciones de Microsoft para configurar SharePoint sitios de equipo en niveles crecientes de protección, empezando por la protección de línea base. Para obtener más información, consulte [Recomendaciones de directivas para proteger SharePoint sitios y archivos](sharepoint-file-access-policies.md).

SharePoint sitios de equipo configurados en el nivel de línea base permiten compartir archivos con usuarios externos mediante vínculos de acceso anónimos. Este enfoque se recomienda en lugar de enviar archivos por correo electrónico.

Para admitir los objetivos de protección de línea base, configure las directivas de uso compartido de todo el inquilino como se recomienda aquí. La configuración de uso compartido de sitios individuales puede ser más restrictiva que esta directiva para todo el inquilino, pero no más permisiva.

|Área|Incluye una directiva predeterminada|Recomendación|
|---|---|---|
|**Uso compartido** (SharePoint en línea y OneDrive para la Empresa)|Sí|El uso compartido externo está habilitado de forma predeterminada. Se recomienda esta configuración: <ul><li>Permitir el uso compartido para usuarios externos autenticados y usar vínculos de acceso anónimo (configuración predeterminada).</li><li>Los vínculos de acceso anónimo expiran en estos días. Escriba un número, si lo desea, como 30 días.</li><li>Tipo de vínculo predeterminado: seleccione Interno (solo personas de la organización). Los usuarios que deseen compartir mediante vínculos anónimos deben elegir esta opción en el menú compartir.</li></ul> <p> Más información: [Introducción al uso compartido externo](/sharepoint/external-sharing-overview)|

SharePoint centro de administración y OneDrive para la Empresa centro de administración incluyen la misma configuración. La configuración de cualquiera de los centros de administración se aplica a ambos.

## <a name="configure-settings-in-azure-active-directory"></a>Configuración de opciones en Azure Active Directory

Asegúrese de visitar estas dos áreas en Azure Active Directory para completar la configuración de todo el inquilino para entornos más seguros.

### <a name="configure-named-locations-under-conditional-access"></a>Configurar ubicaciones con nombre (con acceso condicional)

Si su organización incluye oficinas con acceso seguro a la red, agregue los intervalos de direcciones IP de confianza a Azure Active Directory como ubicaciones con nombre. Esta característica ayuda a reducir el número de falsos positivos notificados para los eventos de riesgo de inicio de sesión.

Consulte: [Ubicaciones con nombre en Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicaciones que no admiten la autenticación moderna

La autenticación multifactor requiere aplicaciones que admitan la autenticación moderna. Las aplicaciones que no admiten la autenticación moderna no se pueden bloquear mediante reglas de acceso condicional.

Para entornos seguros, asegúrese de deshabilitar la autenticación para las aplicaciones que no admiten la autenticación moderna. Puede hacerlo en Azure Active Directory con un control que estará disponible próximamente.

Mientras tanto, use uno de los métodos siguientes para lograr esto para SharePoint Online y OneDrive para la Empresa:

- Use PowerShell; consulte [Bloquear aplicaciones que no usan la autenticación moderna](/mem/intune/protect/app-modern-authentication-block).
- Configúrelo en el <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">centro de administración de SharePoint</a> en la página "Acceso al dispositivo": "Controlar el acceso desde aplicaciones que no usan la autenticación moderna". Elija Bloquear.

## <a name="get-started-with-defender-for-cloud-apps-or-office-365-cloud-app-security"></a>Comenzar con Defender for Cloud Apps o Office 365 Cloud App Security

Use Office 365 Cloud App Security para evaluar el riesgo, para alertar sobre actividades sospechosas y para tomar medidas automáticamente. Requiere Office 365 E5 plan.

O bien, use Microsoft Defender for Cloud Apps para obtener una visibilidad más profunda incluso después de conceder acceso, controles completos y protección mejorada para todas las aplicaciones en la nube, incluidos los Office 365.

Dado que esta solución recomienda el plan EMS E5, se recomienda empezar con Defender for Cloud Apps para que pueda usarlo con otras aplicaciones SaaS de su entorno. Comience con las directivas y la configuración predeterminadas.

Más información:

- [Implementar Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security)
- [Más información sobre Microsoft Defender for Cloud Apps](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [¿Qué es Defender for Cloud Apps?](/cloud-app-security/what-is-cloud-app-security)

:::image type="content" source="../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png" alt-text="Panel de aplicaciones de Defender for Cloud" lightbox="../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png":::

## <a name="additional-resources"></a>Recursos adicionales

Estos artículos y guías proporcionan información prescriptiva adicional para proteger el entorno de Microsoft 365:

- [Guía de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (puede usar estas recomendaciones en cualquier entorno, especialmente en entornos solo en la nube).

- [Directivas y configuraciones de seguridad recomendadas para identidades y dispositivos](microsoft-365-policies-configurations.md) (estas recomendaciones incluyen ayuda para entornos de AD FS)
