---
title: Revise los requisitos de arquitectura y los conceptos de planeamiento de Microsoft Defender para Office 365
description: El diagrama técnico de Microsoft Defender para Office 365 en Microsoft 365 Defender le ayudará a comprender la identidad en Microsoft 365 antes de crear el laboratorio de prueba o el entorno piloto.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 59486fdc30fa512f10126313076fc0be7ff257f5
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67796794"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Revisión de los requisitos de arquitectura de Microsoft Defender para Office 365 y los conceptos clave

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 1 del 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-office-365-overview.md).

Antes de habilitar Defender para Office 365, asegúrese de comprender la arquitectura y de que puede cumplir los requisitos. En este artículo se describen la arquitectura, los conceptos clave y los requisitos previos que debe cumplir el entorno de Exchange Online.

## <a name="understand-the-architecture"></a>Información sobre la arquitectura

En el diagrama siguiente se muestra la arquitectura de línea base para Microsoft Defender para Office, que puede incluir una puerta de enlace SMTP de terceros o una integración local. Los escenarios de coexistencia híbrida (es decir, los buzones de producción son locales y en línea) requieren configuraciones más complejas y no se tratan en este artículo ni en las instrucciones de evaluación.

:::image type="content" source="../../media/defender/m365-defender-office-architecture.png" alt-text="Arquitectura de la Microsoft Defender para Office 365." lightbox="../../media/defender/m365-defender-office-architecture.png":::

En la tabla siguiente se describe esta ilustración.

|Llamada|Descripción|
|---|---|
|1|El servidor host para el remitente externo normalmente realiza una búsqueda dns pública para un registro MX, que proporciona el servidor de destino para retransmitir el mensaje. Esta referencia puede ser Exchange Online (EXO) directamente o una puerta de enlace SMTP que se ha configurado para retransmitir en EXO.|
|2|Exchange Online Protection negocia y valida la conexión entrante e inspecciona los encabezados y el contenido del mensaje para determinar qué directivas, etiquetado o procesamiento adicionales son necesarios.|
|3|Exchange Online se integra con Microsoft Defender para Office 365 para ofrecer protección contra amenazas, mitigación y corrección más avanzadas.|
|4|Un mensaje que no es malintencionado, bloqueado o en cuarentena se procesa y entrega al destinatario en EXO donde se evalúan y desencadenan las preferencias de usuario relacionadas con el correo no deseado, las reglas de buzón de correo u otra configuración.|
|5|La integración con Active Directory local se puede habilitar mediante Azure AD Connect para sincronizar y aprovisionar cuentas y objetos habilitados para correo en Azure Active Directory y, en última instancia, Exchange Online.|
|6|Al integrar un entorno local, se recomienda usar un servidor exchange para la administración y administración admitidas de atributos, configuraciones y atributos relacionados con el correo.|
|7 |Microsoft Defender para Office 365 comparte señales a Microsoft 365 Defender para la detección y respuesta extendidas (XDR).|

La integración local es común pero opcional. Si el entorno es solo en la nube, esta guía también le funcionará.

## <a name="understand-key-concepts"></a>Descripción de los conceptos clave

En la tabla siguiente se identificaron conceptos clave que son importantes comprender al evaluar, configurar e implementar Defender para Office 365.

|Concepto|Descripción|Más información|
|---|---|---|
|Exchange Online Protection|Exchange Online Protection (EOP) es el servicio de filtrado basado en la nube que ayuda a proteger su organización contra el correo no deseado y el malware en el correo electrónico. EOP se incluye en todas las licencias de Microsoft 365 que incluyen Exchange Online.|[Información general de Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)|
|Protección antimalware|Las organizaciones con buzones de Exchange Online se protegen automáticamente contra malware.|[Protección contra malware en EOP](../office-365-security/anti-malware-protection.md)|
|Protección contra correo no deseado|Las organizaciones con buzones de Exchange Online se protegen automáticamente contra correo no deseado y correo no deseado.|[Protección contra correo no deseado en EOP](../office-365-security/anti-spam-protection.md)|
|Protección contra phishing|Defender para Office 365 ofrece protección contra suplantación de identidad (phishing) más avanzada relacionada con la suplantación de identidad (phishing), la caza de ballenas, el ransomware y otras actividades malintencionadas.|[Protección contra suplantación de identidad adicional en Microsoft Defender para Office 365](../office-365-security/anti-phishing-protection.md)|
|Protección contra la suplantación de identidad|EOP incluye características para ayudar a proteger su organización frente a remitentes falsificados (falsificados).|[Protección contra la suplantación de identidad en EOP](../office-365-security/anti-spoofing-protection.md)|
|Datos adjuntos seguros|Datos adjuntos seguros proporciona una capa adicional de protección mediante el uso de un entorno virtual para comprobar y "detonar" los datos adjuntos en los mensajes de correo electrónico antes de que se entreguen.|[Datos adjuntos seguros en Microsoft Defender para Office 365](../office-365-security/safe-attachments.md)|
|Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams|Además, Los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams ofrecen una capa adicional de protección para los archivos que se han cargado en repositorios de almacenamiento en la nube.|[Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](../office-365-security/mdo-for-spo-odb-and-teams.md)|
|Vínculos seguros|Vínculos seguros es una característica que proporciona examen y reescritura de direcciones URL dentro de los mensajes de correo electrónico entrantes y ofrece la verificación de esos vínculos antes de que se entreguen o se haga clic en ellos.|[Vínculos seguros en Microsoft Defender para Office 365](../office-365-security/safe-links.md)|

Para obtener información más detallada sobre las funcionalidades incluidas con Microsoft Defender para Office, consulte [Microsoft Defender para Office 365 descripción del servicio](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="review-architecture-requirements"></a>Revisión de los requisitos de arquitectura

Una evaluación correcta Defender para Office 365 o un piloto de producción asume los siguientes requisitos previos:

- Todos los buzones de correo de destinatario están actualmente en Exchange Online.
- El registro MX público se resuelve directamente en EOP o en una puerta de enlace SMTP de terceros que, a continuación, retransmite el correo electrónico externo entrante directamente a EOP.
- El dominio de correo electrónico principal está configurado como *autoritativo* en Exchange Online.
- Implementó y configuró correctamente *el bloqueo perimetral basado en directorios* (DBEB) según corresponda. Para obtener más información, vea [Usar Directory-Based bloqueo perimetral para rechazar los mensajes enviados a destinatarios no válidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

> [!IMPORTANT]
> Si estos requisitos no son aplicables o sigue en un escenario de coexistencia híbrida, una evaluación de Microsoft Defender para Office 365 puede requerir configuraciones más complejas o avanzadas que no estén completamente cubiertas en esta guía.

## <a name="siem-integration"></a>Integración de SIEM

Puede integrar Microsoft Defender para Office 365 con Microsoft Sentinel para analizar de forma más completa los eventos de seguridad en toda la organización y crear cuadernos de estrategias para obtener una respuesta eficaz e inmediata. Para obtener más información, consulte [Conexión de alertas desde Microsoft Defender para Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection).

Microsoft Defender para Office 365 también se pueden integrar en otras soluciones de administración de eventos e información de seguridad (SIEM) mediante la [API de administración de actividad de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

## <a name="next-steps"></a>Pasos siguientes

Paso 2 de 3: [Habilitar el entorno de evaluación Microsoft Defender para Office 365](eval-defender-office-365-enable-eval.md)

Vuelva a la introducción para [Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
