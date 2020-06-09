---
title: Información general de Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo Exchange Online Protection (EOP) puede ayudar a proteger su organización de correo electrónico local en entornos híbridos y independientes.
ms.openlocfilehash: a3f71ea5366224465cdaf3922c6c467fcb49f3cc
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616991"
---
# <a name="exchange-online-protection-overview"></a>Información general de Exchange Online Protection

Exchange Online Protection (EOP) es el servicio de filtrado basado en la nube que ayuda a proteger la organización contra el correo no deseado y el malware. EOP se incluye en todas las organizaciones de Microsoft 365 con buzones de correo de Exchange Online.

Pero EOP también está disponible en los siguientes escenarios locales:

- **En un escenario independiente**: EOP proporciona protección de correo electrónico basada en la nube para su organización de Exchange local o para cualquier otra solución de correo SMTP local.

- **En una implementación híbrida**: EOP se puede configurar para proteger su entorno de correo electrónico y controlar el enrutamiento de correo cuando tiene una mezcla de buzones locales y en la nube.

En estos escenarios, EOP puede simplificar la administración de su entorno de correo electrónico y aliviar muchas de las cargas que se incluyen en el mantenimiento de hardware y software local.

El resto de este tema explica cómo funciona EOP en entornos independientes e híbridos.

## <a name="how-eop-works"></a>Cómo funciona EOP

Para comprender el funcionamiento de EOP, es muy útil ver cómo se procesa el correo entrante:

![Diagrama del proceso de correo electrónico](../../media/emailprocessingineop1.png)

- Un mensaje entrante pasa inicialmente por el filtrado de conexiones, que comprueba la reputación del remitente e inspecciona el mensaje en busca de malware. En este punto, la mayoría de los correos no deseados se interrumpen y se eliminan mediante EOP. Para obtener más información, consulte [Configurar filtrado de la conexión](configure-the-connection-filter-policy.md).

- Los mensajes continúan a través del filtrado de directivas, donde los mensajes se evalúan con reglas de flujo de correo personalizado (también conocidas como reglas de transporte) que se crean o aplican a partir de una plantilla. Por ejemplo, puede tener una regla que envíe una notificación a un administrador cuando llegue el correo de un remitente específico. Las comprobaciones de prevención de pérdida de datos (DLP) también se producen en este punto (Exchange Enterprise CAL con servicios).

- A continuación, los mensajes pasan a través del filtrado contra correo no deseado (también conocido como filtrado de contenido). Un mensaje que se determina como correo no deseado se puede enviar a la carpeta de correo no deseado o a la cuarentena de un usuario, entre otras opciones. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

- Una vez que un mensaje pasa todas estas capas de protección correctamente, se entrega al destinatario.

Para obtener más información, consulte [Order and Precedence of email Protection](how-policies-and-protections-are-combined.md).

### <a name="eop-datacenters"></a>Centros de datos de EOP

EOP se ejecuta en una red mundial de centros de datos que están diseñados para proporcionar la mejor disponibilidad. Por ejemplo, si un centro de datos no está disponible, los mensajes de correo electrónico se enrutan automáticamente a otro centro de datos sin interrupciones del servicio. Los servidores de cada centro de recursos aceptan mensajes en su nombre, lo que proporciona una capa de separación entre la organización e Internet, con lo que se reduce la carga en los servidores. Gracias a esta red de alta disponibilidad, Microsoft se asegura que el correo llegue a la organización de manera puntual.

EOP realiza el equilibrio de carga entre los centros de datos, pero solo dentro de una región. Si está aprovisionado en una región, todos sus mensajes se procesarán usando el enrutamiento de correo de esa región. La siguiente lista muestra cómo funciona el enrutamiento regional de correo para los centros de datos de EOP:

- En Europa, Oriente Medio y África (EMEA), todos los buzones de Exchange Online están ubicados en centros de datos de EMEA, y todos los mensajes se enrutan a través de EMEA para el filtrado de EOP.

- En Asia-Pacífico (APAC), todos los buzones de correo de Exchange Online se encuentran en centros de recursos de APACciones y los mensajes se enrutan actualmente a través de centros de recursos de APAC para el filtrado de EOP.

- En América, todos los buzones de correo de Exchange Online se encuentran en centros de seguridad de Estados Unidos, con la excepción de Sudamérica, donde se usan centros de recursos de Brasil y Chile y en Canadá, en los que se usan centros de conexión de Canadá. Todos los mensajes de correo electrónico, incluidos los mensajes para clientes de Sudamérica y Canadá, se enrutan a través de centros de recursos locales para el filtrado de EOP; el correo electrónico en cuarentena se almacena en el centro de almacenamiento en el que se encuentra el inquilino.

- Para la nube de la comunidad de organismos oficiales (GCC), todos los buzones de Exchange Online están ubicados en centros de datos de Estados Unidos y los mensajes se enrutan a través de centros de datos de Estados Unidos para el filtrado de EOP.

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Planes y características de EOP para organizaciones de correo electrónico locales

Los planes de suscripción de EOP disponibles son los siguientes:

- **EOP independiente**: debe inscribirse en EOP para proteger su organización de correo electrónico local.

- **Características de EOP en Exchange Online**: cualquier suscripción que incluya Exchange Online (independiente o como parte de Microsoft 365) utiliza EOP para proteger los buzones de correo de Exchange Online.

- **Exchange Enterprise cal con servicios**: Si tiene una organización de Exchange local en la que ha comprado otras licencias de Exchange Enterprise cal con servicios, EOP forma parte de los servicios incluidos.

Para obtener información acerca de los requisitos, límites importantes y disponibilidad de características en todos los planes de suscripción de EOP, vea la [Descripción del servicio protección en línea de Exchange](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configuración de EOP para organizaciones de correo electrónico locales

Configurar EOP puede ser fácil, especialmente en las compañías pequeñas con pocas reglas de cumplimiento. Sin embargo, si tiene una organización grande con muchos dominios, reglas de cumplimiento personalizadas o flujo de correo híbrido, la configuración puede llevar más tiempo e implicar más planeación.

Si ya ha comprado EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md) para asegurarse de completar todos los pasos necesarios para configurar EOP de modo que proteja el entorno de mensajería.

## <a name="eop-help-for-admins"></a>Ayuda de EOP para administradores

El contenido de la Ayuda para administradores de EOP consta de las siguientes categorías principales:

- [Exchange Online Protection Overview](exchange-online-protection-overview.md): presenta cómo funciona EOP y proporciona vínculos a información adicional.

- [Características de EOP](eop-features.md): proporciona una lista de las características que están disponibles en EOP.

- [Configurar el servicio de EOP](set-up-your-eop-service.md): proporciona los pasos para configurar el servicio de EOP y vínculos a información adicional.

- [Cambiar a EOP desde Google Postini, Barracuda Spam y virus firewall o Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): describe el proceso para cambiar a EOP desde otro producto de protección de correo electrónico.

- [Administrar destinatarios en EOP independiente](manage-recipients-in-eop.md): describe cómo administrar usuarios y grupos de correo en EOP.

- [Flujo de correo en EOP](mail-flow-in-eop.md): describe cómo configurar escenarios de flujo de correo personalizados mediante conectores, cómo administrar dominios asociados con el servicio y cómo habilitar la característica de bloqueo perimetral basado en directorios (DBEB).

- [Best Practices for Configuring EOP](best-practices-for-configuring-eop.md): describe las opciones de configuración recomendadas para después de configurar y aprovisionar el servicio.

- [Informes de auditoría en EOP independiente](auditing-reports-in-eop.md): describe cómo usar los informes de auditoría para realizar un seguimiento de los cambios de configuración en el servicio.

- [Protección contra correo electrónico no deseado y antimalware en EOP](anti-spam-and-anti-malware-protection.md): describe el filtrado de correo no deseado y el filtrado de malware y muestra cómo personalizarlos para satisfacer mejor las necesidades de su organización. También se describen las tareas que los administradores y los usuarios finales pueden realizar en los mensajes en cuarentena.

- [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): describe los informes y las herramientas de solución de problemas que están disponibles.

- [Centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md): describe cómo tener acceso y navegar por la interfaz de administración del centro de administración de Exchange (EAC) para administrar el servicio de EOP.

- [PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): proporciona información sobre PowerShell remoto, que permite administrar el servicio EOP desde la línea de comandos.

- [Ayuda y soporte técnico para EOP](help-and-support-for-eop.md) Proporciona información sobre cómo obtener ayuda y soporte técnico.
