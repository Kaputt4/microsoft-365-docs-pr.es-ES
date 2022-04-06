---
title: Revisar los requisitos de arquitectura y los conceptos de planeación para Microsoft Defender para Office 365
description: El diagrama técnico de Microsoft Defender para Office 365 en Microsoft 365 Defender le ayudará a comprender la identidad en Microsoft 365 antes de crear el entorno piloto o el laboratorio de prueba.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0ce03f919d3a4012952ab7d2056b33f2eeb71926
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569477"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Revisar Microsoft Defender para Office 365 de arquitectura y conceptos clave


**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 1 de 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-office-365-overview.md).

Antes de Defender para Office 365, asegúrese de comprender la arquitectura y de cumplir los requisitos. En este artículo se describen la arquitectura, los conceptos clave y los requisitos previos que debe cumplir Exchange Online entorno.

## <a name="understand-the-architecture"></a>Información sobre la arquitectura

En el siguiente diagrama se muestra la arquitectura de línea base de Microsoft Defender para Office, que puede incluir una puerta de enlace SMTP de terceros o una integración local. Los escenarios de coexistencia híbrida (es decir, los buzones de producción son locales y en línea) requieren configuraciones más complejas y no se tratan en este artículo ni en las instrucciones de evaluación.

:::image type="content" source="../../media/defender/m365-defender-office-architecture.png" alt-text="La arquitectura de la Microsoft Defender para Office 365" lightbox="../../media/defender/m365-defender-office-architecture.png":::

En la tabla siguiente se describe esta ilustración.

|Llamada  |Descripción  |
|---------|---------|
|1     | El servidor host del remitente externo suele realizar una búsqueda de DNS pública para un registro MX, que proporciona al servidor de destino para retransmitir el mensaje.  Esta referencia puede ser Exchange Online (EXO) directamente o una puerta de enlace SMTP que se ha configurado para retransmitir con EXO.  |
|2     | Exchange Online Protection negocia y valida la conexión entrante e inspecciona los encabezados y el contenido del mensaje para determinar qué directivas adicionales, etiquetado o procesamiento son necesarios.  |
|3     | Exchange Online se integra con Microsoft Defender para Office 365 para ofrecer una protección, mitigación y corrección de amenazas más avanzada. |
|4     | Un mensaje que no es malintencionado, bloqueado o en cuarentena se procesa y entrega al destinatario en EXO donde las preferencias del usuario relacionadas con el correo no deseado, las reglas de buzón u otras opciones de configuración se evalúan y desencadenan. |
|5     | La integración con Active Directory local se puede habilitar mediante Azure AD Conectar para sincronizar y aprovisionar objetos y cuentas habilitados para correo para Azure Active Directory y, en última instancia, Exchange Online. |
|6      | Al integrar un entorno local, se recomienda usar un servidor Exchange para la administración y administración compatibles de atributos, configuraciones y configuraciones relacionados con el correo |
|7      | Microsoft Defender para Office 365 comparte señales a Microsoft 365 Defender para la detección y respuesta extendidas (XDR).|

La integración local es común pero opcional. Si el entorno es solo en la nube, esta guía también funcionará para usted.

## <a name="understand-key-concepts"></a>Comprender conceptos clave

En la siguiente tabla se identificaron conceptos clave que son importantes para comprender al evaluar, configurar e implementar MDO.


|Concepto  |Descripción |Más información  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP) es el servicio de filtrado basado en la nube que ayuda a proteger su organización contra correo electrónico no deseado y malware. EOP se incluye en todas las Microsoft 365 licencias que incluyen Exchange Online.     |   [Información general de Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)      |
|Protección antimalware     |    Las organizaciones con buzones en EXO se protegen automáticamente contra malware.     |  [Protección contra malware en EOP](../office-365-security/anti-malware-protection.md)       |
|Protección contra correo no deseado     |   Las organizaciones con buzones en EXO se protegen automáticamente contra el correo no deseado y las directivas de correo no deseado.      |  [Protección contra correo no deseado en EOP](../office-365-security/anti-spam-protection.md)       |
|Protección contra phishing |  MDO ofrece una protección contra suplantación de identidad más avanzada relacionada con la suplantación de identidad de lanza, la caza de ballenas, el ransomware y otras actividades malintencionadas.   | [Protección contra suplantación de identidad adicional en Microsoft Defender para Office 365](../office-365-security/anti-phishing-protection.md)   |
|Protección contra la suplantación de identidad     |   EOP incluye características que ayudan a proteger su organización de remitentes falsificados (falsificados).      |   [Protección contra la suplantación de identidad en EOP](../office-365-security/anti-spoofing-protection.md)      |
|Datos adjuntos seguros     |   Caja fuerte datos adjuntos proporciona una capa adicional de protección mediante el uso de un entorno virtual para comprobar y "detonar" los datos adjuntos en los mensajes de correo electrónico antes de que se entreguen.      |   [Caja fuerte datos adjuntos en Microsoft Defender para Office 365](../office-365-security/safe-attachments.md)      |
|Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams     |    Además, Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams ofrece una capa adicional de protección para los archivos que se han cargado en repositorios de almacenamiento en la nube.     |  [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|Vínculos seguros     | Caja fuerte links es una característica que proporciona análisis y reescritura de direcciones URL dentro de los mensajes de correo electrónico entrantes y ofrece verificación de dichos vínculos antes de que se entreguen o se haga clic en ellos.        |   [Caja fuerte vínculos en Microsoft Defender para Office 365](../office-365-security/safe-links.md)      |
|    |         |         |

Para obtener información más detallada acerca de las funcionalidades incluidas con Microsoft Defender para Office, [consulte Microsoft Defender para Office 365 descripción del servicio](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="review-architecture-requirements"></a>Revisión de los requisitos de arquitectura
Un piloto de producción o evaluación de MDO correcto asume los siguientes requisitos previos:
- Todos los buzones de destinatarios están actualmente en Exchange Online.
- El registro MX público se resuelve directamente en EOP o en una puerta de enlace SMTP de terceros que, a continuación, retransmite el correo electrónico externo entrante directamente a EOP.
- El dominio de correo electrónico principal está configurado como *autoritativo* en Exchange Online.
- Implementó y configuró correctamente el bloqueo perimetral basado en *directorios* (DBEB) según corresponda. Para obtener más información, vea [Use Directory-Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

> [!IMPORTANT]
> Si estos requisitos no son aplicables o aún se encuentra en un escenario de coexistencia híbrida, una evaluación de Microsoft Defender para Office 365 puede requerir configuraciones más complejas o avanzadas que no están totalmente cubiertas en esta guía.

## <a name="siem-integration"></a>Integración de SIEM

Puedes integrar Microsoft Defender para Office 365 con Microsoft Sentinel para analizar más exhaustivamente los eventos de seguridad en toda la organización y crear libros de juegos para obtener una respuesta eficaz e inmediata. Para obtener más información, [vea Conectar alertas desde Microsoft Defender para Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection).

Microsoft Defender para Office 365 también se puede integrar en otras soluciones de administración de eventos y de información de seguridad (SIEM) mediante la API de administración Office 365 [actividad](/office/office-365-management-api/office-365-management-activity-api-reference).

## <a name="next-steps"></a>Siguientes pasos

Paso 2 de 3: [Habilitar el entorno de evaluación Microsoft Defender para Office 365](eval-defender-office-365-enable-eval.md)

Vuelva a la introducción a [Evaluate Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) 
