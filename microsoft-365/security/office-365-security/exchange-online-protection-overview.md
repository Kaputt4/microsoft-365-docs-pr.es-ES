---
title: Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre Exchange Online Protection (EOP) puede ayudar a proteger su organización de correo electrónico local en entornos independientes e híbridos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624729"
---
# <a name="exchange-online-protection-overview"></a>Información general de Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) es el servicio de filtrado basado en la nube que ayuda a proteger su organización contra correo no deseado, malware y otras amenazas de correo electrónico. EOP se incluye en todas las Microsoft 365 con Exchange Online buzones de correo.

El resto de este artículo explica cómo funciona EOP.

> [!NOTE]
> EOP también está disponible por sí mismo para proteger los buzones locales y en entornos híbridos para proteger los buzones de correo Exchange locales. Para obtener más información, vea [Standalone Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).

## <a name="how-eop-works"></a>Cómo funciona EOP

Para comprender el funcionamiento de EOP, es muy útil ver cómo se procesa el correo entrante:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Gráfico del correo electrónico de Internet o los comentarios del cliente que pasan a EOP y a través de la conexión, antimalware, el filtrado de reglas de barras diagonales de flujo de correo y el filtrado de contenido, antes del veredicto de correo no deseado o cuarentena, o la entrega de correo del usuario final.":::

- Cuando un mensaje entrante entra en EOP, pasa inicialmente a través del filtrado de conexiones, lo que comprueba la reputación del remitente. La mayoría del correo no deseado se detiene en este momento y EOP lo rechaza. Para obtener más información, consulte [Configurar filtrado de la conexión](configure-the-connection-filter-policy.md).

- A continuación, se inspecciona el mensaje en busca de malware. Si se encuentra malware en el mensaje o en los datos adjuntos, el mensaje se enruta a un almacén de cuarentena de solo administrador. Para obtener más información acerca de la protección contra malware, vea [Protección contra malware en EOP](anti-malware-protection.md).

- Los mensajes continúan a través del filtrado de directivas, donde se evalúan con las reglas de flujo de correo personalizadas (también conocidas como reglas de transporte) que se crean o aplican desde una plantilla. Por ejemplo, puede tener una regla que envíe una notificación a un administrador cuando el correo llegue de un remitente específico. Las comprobaciones de prevención de pérdida de datos (DLP) también se realizan en este momento (Exchange Enterprise CAL con servicios).

- A continuación, el mensaje pasa a través del filtrado contra correo no deseado donde el mensaje está buscando correo no deseado, suplantación de identidad o correo electrónico masivo. Los mensajes detectados se pueden enviar a la cuarentena o a la carpeta correo no deseado de un usuario, entre otras opciones. Para obtener más información, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md) y [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).

Cualquier mensaje que pase todas estas capas de protección correctamente se entregará al destinatario.

Para obtener más información, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Planes y características de EOP para organizaciones de correo electrónico locales

Los planes de suscripción de EOP disponibles son:

- **EOP independiente:** se inscribe en EOP para proteger su organización de correo electrónico local.

- Características de EOP en **Exchange Online:** cualquier suscripción que incluya Exchange Online (independiente o como parte de Microsoft 365) usa EOP para proteger los buzones Exchange Online correo.

- **Exchange Enterprise CAL** con servicios: si tiene una organización de Exchange local en la que ha adquirido licencias de Exchange Enterprise CAL con servicios, EOP forma parte de los servicios incluidos.

Para obtener información sobre los requisitos, los límites importantes y la disponibilidad de características en todos los planes de suscripción de EOP, consulte [la Exchange Online Protection del servicio](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

> [!NOTE]
> Si tiene una suscripción Microsoft 365 o Office 365 que incluye Exchange Online buzones de correo, tiene EOP. Para ver los pasos para configurar las características de seguridad de EOP en la suscripción y la información sobre la seguridad agregada que puede proporcionar una suscripción de Microsoft Defender para Office 365, consulte [Protect against threats](protect-against-threats.md). La configuración recomendada para la característica EOP para la configuración se encuentra en Configuración recomendada para EOP y Microsoft Defender para Office 365 [seguridad.](recommended-settings-for-eop-and-office365.md)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configurar EOP para organizaciones de correo electrónico locales

Configurar EOP puede ser fácil, especialmente en las compañías pequeñas con pocas reglas de cumplimiento. Sin embargo, si tiene una organización grande con muchos dominios, reglas de cumplimiento personalizadas o flujo de correo híbrido, la configuración puede llevar más tiempo e implicar más planeación.

Si ya ha comprado EOP, vea [Configurar un servicio de EOP](/exchange/standalone-eop/set-up-your-eop-service) para asegurarse de completar todos los pasos necesarios para configurar EOP de modo que proteja el entorno de mensajería.

### <a name="eop-datacenters"></a>Centros de datos de EOP

EOP se ejecuta en una red mundial de centros de datos que están diseñados para proporcionar la mejor disponibilidad. Por ejemplo, si un centro de datos no está disponible, los mensajes de correo electrónico se enrutan automáticamente a otro centro de datos sin interrupciones del servicio. Los servidores de cada centro de datos aceptan mensajes en su nombre, lo que proporciona una capa de separación entre su organización e Internet, lo que reduce la carga en los servidores. Gracias a esta red de alta disponibilidad, Microsoft se asegura que el correo llegue a la organización de manera puntual.

EOP realiza el equilibrio de carga entre los centros de datos, pero solo dentro de una región. Si está aprovisionado en una región, todos sus mensajes se procesarán usando el enrutamiento de correo de esa región. La siguiente lista muestra cómo funciona el enrutamiento regional de correo para los centros de datos de EOP:

- En Europa, Oriente Medio y África (EMEA), todos los buzones de Exchange Online están ubicados en centros de datos de EMEA, y todos los mensajes se enrutan a través de EMEA para el filtrado de EOP.
- En Asia-Pacific (APAC), todos los buzones de correo Exchange Online se encuentran en centros de datos de APAC y los mensajes se enruta actualmente a través de centros de datos de APAC para el filtrado de EOP.
- En América, los servicios se distribuyen en las siguientes ubicaciones:
  - Sudamérica: Exchange Online buzones de correo se encuentran en centros de datos en Brasil y Chile. Todos los mensajes se enruta a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.
  - Canadá: Exchange Online buzones de correo se encuentran en centros de datos en Canadá. Todos los mensajes se enruta a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.
  - Estados Unidos: Exchange Online buzones de correo se encuentran en centros de datos de Estados Unidos. Todos los mensajes se enruta a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.
- Para la nube de la comunidad de organismos oficiales (GCC), todos los buzones de Exchange Online están ubicados en centros de datos de Estados Unidos y los mensajes se enrutan a través de centros de datos de Estados Unidos para el filtrado de EOP.

## <a name="eop-help-for-admins"></a>Ayuda de EOP para administradores

El contenido de la Ayuda para administradores de EOP consta de las siguientes categorías principales:

- [Configurar EOP, día 1,](protect-against-threats.md)para Microsoft Defender para administradores de Office 365: Configuración de herramientas de protección y detección de EOP en el centro de Microsoft Defender para Office 365.

- [Características de EOP:](eop-features.md)proporciona una lista de características que están disponibles en EOP.

- [Configurar el servicio EOP:](/exchange/standalone-eop/set-up-your-eop-service)proporciona pasos para configurar el servicio de EOP y vínculos a información adicional.

- Cambie a EOP desde Google Postini, el Firewall de virus y correo no deseado de [Barracuda o Cisco IronPort:](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)describe el proceso para cambiar a EOP desde otro producto de protección de correo electrónico.

- [Administrar destinatarios en EOP independiente:](/exchange/standalone-eop/manage-recipients-in-eop)describe cómo administrar usuarios y grupos de correo en EOP independiente.

- Flujo de correo en [EOP:](mail-flow-in-eop.md)describe cómo configurar escenarios de flujo de correo personalizados con conectores, cómo administrar dominios asociados con el servicio y cómo habilitar la característica de bloqueo perimetral basado en directorios (DBEB).

- [Configuración recomendada para EOP](recommended-settings-for-eop-and-office365.md)y Microsoft Defender para la seguridad Office 365: describe las opciones de configuración recomendadas y consideraciones para después de configurar y aprovisionar el servicio.

- [Informes de auditoría en Exchange Online:](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)describe cómo usar informes de auditoría para realizar un seguimiento de los cambios de configuración en el servicio.

- Protección contra correo no deseado y antimalware en [EOP:](anti-spam-and-anti-malware-protection.md)describe el filtrado de correo no deseado y el filtrado de malware y muestra cómo personalizarlos para satisfacer mejor las necesidades de su organización. También se describen las tareas que los administradores y los usuarios finales pueden realizar en los mensajes en cuarentena.

- [Informes y seguimiento de mensajes en Exchange Online Protection:](reporting-and-message-trace-in-exchange-online-protection.md)describe los informes y las herramientas de solución de problemas que están disponibles.

- [Exchange](/exchange/exchange-admin-center) centro de administración de Exchange Online o centro de administración de Exchange en [EOP](/exchange/standalone-eop/exchange-admin-center-eop)independiente: describe cómo acceder y navegar por la interfaz de administración del Centro de administración de Exchange (EAC) para administrar las características relacionadas de EOP.

- [Exchange Online Protection PowerShell:](/powershell/exchange/exchange-online-protection-powershell)proporciona información sobre PowerShell remoto, que le permite administrar el servicio EOP desde la línea de comandos.

- [Ayuda y soporte técnico para EOP](help-and-support-for-eop.md) Proporciona información sobre cómo obtener ayuda y soporte técnico.