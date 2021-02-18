---
title: Introducción a Exchange Online Protection (EOP)
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
description: Obtenga información sobre cómo Exchange Online Protection (EOP) puede ayudar a proteger su organización de correo electrónico local en entornos híbridos e independientes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8e3d44cb39e3569179d4155e32a8c11e0a5be56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286890"
---
# <a name="exchange-online-protection-overview"></a>Información general de Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) es el servicio de filtrado basado en la nube que ayuda a proteger su organización contra correo no deseado y malware. EOP se incluye en todas las organizaciones de Microsoft 365 con buzones de Exchange Online. Sin embargo, EOP también está disponible en los siguientes escenarios locales:

- **En un escenario independiente:** EOP proporciona protección de correo electrónico basada en la nube para su organización de Exchange local o para cualquier otra solución de correo electrónico SMTP local.

- **En una implementación híbrida:** EOP se puede configurar para proteger su entorno de correo electrónico y controlar el enrutamiento de correo cuando tiene una combinación de buzones locales y en la nube.

En estos escenarios, EOP puede simplificar la administración de su entorno de correo electrónico y aliviar muchas de las cargas que se incluyen con el mantenimiento de hardware y software local.

En el resto de este tema se explica cómo funciona EOP en entornos híbridos e independientes.

## <a name="how-eop-works"></a>Cómo funciona EOP

Para comprender el funcionamiento de EOP, es muy útil ver cómo se procesa el correo entrante:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Gráfico de correo electrónico de Internet o comentarios de clientes que pasan a EOP y a través de la conexión, antimalware, filtrado de directivas de barra diagonal de flujo de correo y filtrado de contenido, antes del veredicto de correo no deseado, cuarentena o entrega de correo del usuario final.":::

- Cuando un mensaje entrante entra en EOP, inicialmente pasa a través del filtrado de conexiones, lo que comprueba la reputación del remitente. La mayoría del correo no deseado se detiene en este punto y EOP lo rechaza. Para obtener más información, consulte [Configurar filtrado de la conexión](configure-the-connection-filter-policy.md).

- A continuación, se inspecciona el mensaje en busca de signos de malware. Si se encuentra malware en el mensaje o en los datos adjuntos, el mensaje se enruta a un almacén de cuarentena de solo administrador. Puede obtener más información sobre cómo configurar antimalware [aquí.](configure-anti-malware-policies.md)

- Los mensajes continúan mediante el filtrado de directivas, donde se evalúan con las reglas de flujo de correo personalizadas (también conocidas como reglas de transporte) que se crean o aplican desde una plantilla. Por ejemplo, puede tener una regla que envíe una notificación a un administrador cuando llegue el correo de un remitente específico. Las comprobaciones de prevención de pérdida de datos (DLP) también se realizan en este momento (Exchange Enterprise CAL con servicios).

- A continuación, el mensaje pasa por el filtrado de contenido (también conocido como correo no deseado). Un mensaje que este filtro determina que es correo no deseado o *suplantación* de identidad se puede enviar a la cuarentena, o la carpeta de correo no deseado de un usuario, entre otras opciones. Para obtener más información, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).

Todos los mensajes que pasan todas estas capas de protección se entregan correctamente al destinatario.

Para obtener más información, consulte [Orden y prioridad de la protección de correo electrónico.](how-policies-and-protections-are-combined.md)

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Planes y características de EOP para organizaciones de correo electrónico locales

Los planes de suscripción de EOP disponibles son:

- **EOP independiente:** se inscribe en EOP para proteger su organización de correo electrónico local.

- **Características de EOP** en Exchange Online: cualquier suscripción que incluya Exchange Online (independiente o como parte de Microsoft 365) usa EOP para proteger los buzones de Exchange Online.

- **Exchange Enterprise CAL con** servicios: si tiene una organización de Exchange local donde ha adquirido licencias adicionales de Exchange Enterprise CAL con servicios, EOP forma parte de los servicios incluidos.

Para obtener información sobre los requisitos, los límites importantes y la disponibilidad de características en todos los planes de suscripción de EOP, vea la descripción del servicio [Exchange Online Protection.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configuración de EOP para organizaciones de correo electrónico locales

Configurar EOP puede ser fácil, especialmente en las compañías pequeñas con pocas reglas de cumplimiento. Sin embargo, si tiene una organización grande con muchos dominios, reglas de cumplimiento personalizadas o flujo de correo híbrido, la configuración puede llevar más tiempo e implicar más planeación.

Si ya ha comprado EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md) para asegurarse de completar todos los pasos necesarios para configurar EOP de modo que proteja el entorno de mensajería.

### <a name="eop-datacenters"></a>Centros de datos de EOP

EOP se ejecuta en una red mundial de centros de datos que están diseñados para proporcionar la mejor disponibilidad. Por ejemplo, si un centro de datos no está disponible, los mensajes de correo electrónico se enrutan automáticamente a otro centro de datos sin interrupciones del servicio. Los servidores de cada centro de datos aceptan mensajes en su nombre, lo que proporciona una capa de separación entre su organización e Internet, lo que reduce la carga en los servidores. Gracias a esta red de alta disponibilidad, Microsoft se asegura que el correo llegue a la organización de manera puntual.

EOP realiza el equilibrio de carga entre los centros de datos, pero solo dentro de una región. Si está aprovisionado en una región, todos sus mensajes se procesarán usando el enrutamiento de correo de esa región. La siguiente lista muestra cómo funciona el enrutamiento regional de correo para los centros de datos de EOP:

- En Europa, Oriente Medio y África (EMEA), todos los buzones de Exchange Online están ubicados en centros de datos de EMEA, y todos los mensajes se enrutan a través de EMEA para el filtrado de EOP.

- En Asia-Pacific (APAC), todos los buzones de Exchange Online se encuentran en centros de datos de APAC y los mensajes se enruta actualmente a través de centros de datos APAC para el filtrado de EOP.

- En América, los servicios se distribuyen en las siguientes ubicaciones:

  - América del Sur: los buzones de Exchange Online se encuentran en centros de datos de Brasil y Chile. Todos los mensajes se enrutar a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el inquilino.

  - Canadá: los buzones de Exchange Online se encuentran en centros de datos de Canadá. Todos los mensajes se enrutar a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.

  - Estados Unidos: los buzones de Exchange Online se encuentran en centros de datos de Estados Unidos. Todos los mensajes se enrutar a través de centros de datos locales para el filtrado de EOP. Los mensajes en cuarentena se almacenan en el centro de datos donde se encuentra el espacio empresarial.

- Para la nube de la comunidad de organismos oficiales (GCC), todos los buzones de Exchange Online están ubicados en centros de datos de Estados Unidos y los mensajes se enrutan a través de centros de datos de Estados Unidos para el filtrado de EOP.

## <a name="eop-help-for-admins"></a>Ayuda de EOP para administradores

El contenido de la Ayuda para administradores de EOP consta de las siguientes categorías principales:

- Configure EOP, día 1, para los administradores de Microsoft Defender para [Office 365:](protect-against-threats.md)configurar las herramientas de protección y detección de EOP en el centro de Microsoft Defender para Office 365.

- [Características de EOP:](eop-features.md)proporciona una lista de características que están disponibles en EOP.

- [Configurar el servicio EOP:](set-up-your-eop-service.md)proporciona pasos para configurar el servicio de EOP y vínculos a información adicional.

- [Cambie a EOP desde Google Postini, Barracuda Spam and Virus Firewall o Cisco IronPort:](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)describe el proceso para cambiar a EOP desde otro producto de protección de correo electrónico.

- [Administrar destinatarios en EOP independiente:](manage-recipients-in-eop.md)describe cómo administrar usuarios y grupos de correo en EOP.

- Flujo de correo en [EOP:](mail-flow-in-eop.md)describe cómo configurar escenarios de flujo de correo personalizados mediante conectores, cómo administrar dominios asociados con el servicio y cómo habilitar la característica bloqueo perimetral basado en directorios (DBEB).

- [Procedimientos recomendados para configurar EOP:](best-practices-for-configuring-eop.md)describe las opciones de configuración recomendadas y las consideraciones para después de configurar y aprovisionar el servicio.

- [Informes de auditoría en EOP independiente:](auditing-reports-in-eop.md)describe cómo usar informes de auditoría para realizar un seguimiento de los cambios de configuración en el servicio.

- Protección contra correo electrónico no deseado y antimalware en [EOP:](anti-spam-and-anti-malware-protection.md)describe el filtrado de correo no deseado y el filtrado de malware y muestra cómo personalizarlos para satisfacer mejor las necesidades de su organización. También se describen las tareas que los administradores y los usuarios finales pueden realizar en los mensajes en cuarentena.

- [Informes y seguimiento de mensajes en Exchange Online Protection:](reporting-and-message-trace-in-exchange-online-protection.md)describe los informes y las herramientas de solución de problemas disponibles.

- [Centro de administración de Exchange](exchange-admin-center-in-exchange-online-protection-eop.md)en EOP independiente: describe cómo acceder y navegar por la interfaz de administración del Centro de administración de Exchange (EAC) para administrar el servicio EOP.

- [Exchange Online Protection PowerShell:](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)proporciona información sobre PowerShell remoto, que le permite administrar el servicio EOP desde la línea de comandos.

- [Ayuda y soporte técnico para EOP](help-and-support-for-eop.md) Proporciona información sobre cómo obtener ayuda y soporte técnico.
