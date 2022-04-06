---
title: Migrar desde un servicio de protección de terceros a Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Obtenga información sobre la forma correcta de migrar desde dispositivos o servicios de protección de terceros como Google Postini, el Firewall de virus y correo no deseado de Barracuda o Cisco IronPort a Microsoft Defender para Office 365 protección.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba82621e76665ee94d2a182e777ad1d222ef8e56
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477047"
---
# <a name="migrate-from-a-third-party-protection-service-or-device-to-microsoft-defender-for-office-365"></a>Migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Si ya tienes un dispositivo o servicio de protección de terceros existente frente a Microsoft 365, puedes usar esta guía para migrar la protección a Microsoft Defender para Office 365 para obtener las ventajas de una experiencia de administración consolidada, un costo potencialmente reducido (con productos que ya pagas) y un producto maduro con protección de seguridad integrada. Para obtener más información, consulte [Microsoft Defender for Office](https://www.microsoft.com/security/business/threat-protection/office-365-defender).

En esta guía se proporcionan pasos específicos y que pueden realizarse para la migración y se asumen los siguientes hechos:

- Ya tienes Microsoft 365 buzones de correo, pero actualmente estás usando un servicio o dispositivo de terceros para la protección de correo electrónico. El correo de Internet fluye por el servicio de protección antes de la entrega a la organización de Microsoft 365 y la protección de Microsoft 365 es lo más baja posible (nunca está completamente desactivada; por ejemplo, la protección contra malware siempre se aplica).

  :::image type="content" source="../../media/mdo-migration-before.png" alt-text="El correo fluye desde Internet a través del dispositivo o servicio de protección de terceros antes de la entrega en Microsoft 365" lightbox="../../media/mdo-migration-before.png":::

- Está fuera de la fase de investigación y consideración para la protección de Defender para Office 365. Si necesita evaluar Defender para Office 365 decidir si es adecuado para su organización, le recomendamos que considere el [modo de evaluación](office-365-evaluation.md).

- Ya has comprado Defender para Office 365 licencias.

- Debe retirar el servicio de protección de terceros existente, lo que significa que, en última instancia, tendrá que apuntar los registros MX de los dominios de correo electrónico a Microsoft 365. Cuando haya terminado, el correo de Internet fluirá directamente a Microsoft 365 y estará protegido exclusivamente por Exchange Online Protection (EOP) y Defender para Office 365.

  :::image type="content" source="../../media/mdo-migration-after.png" alt-text="El correo fluye de Internet a Microsoft 365" lightbox="../../media/mdo-migration-after.png":::

Eliminar el servicio de protección existente a favor de Defender para Office 365 es un gran paso que no debe tomar a la ligera ni debe apresurarse a realizar el cambio. Las instrucciones de esta guía de migración le ayudarán a realizar una transición ordenada de la protección con una interrupción mínima para los usuarios.

Los pasos de migración de muy alto nivel se ilustran en el siguiente diagrama. Los pasos reales se enumeran en la sección Denominada [Proceso de migración](#the-migration-process) más adelante en este artículo.

:::image type="content" source="../../media/mdo-migration-overview.png" alt-text="El proceso de migración desde una solución de protección de terceros o un dispositivo a Defender para Office 365" lightbox="../../media/mdo-migration-overview.png":::

## <a name="why-use-the-steps-in-this-guide"></a>¿Por qué usar los pasos de esta guía?

En el sector de LA, las sorpresas suelen ser malas. Simplemente voltear los registros MX para apuntar a Microsoft 365 sin pruebas previas y cuidadosas dará lugar a muchas sorpresas. Por ejemplo:

- Es probable que usted o sus predecesores han dedicado mucho tiempo y esfuerzo a personalizar el servicio de protección existente para una entrega de correo óptima (es decir, bloquear lo que debe bloquearse y permitir lo que se debe permitir). Es casi una certeza garantizada que no todas las personalizaciones del servicio de protección actual son necesarias en Defender para Office 365. También es muy posible que Defender para Office 365 presente nuevos problemas (permite o bloques) que no ocurrieron o que no eran necesarios en el servicio de protección actual.
- El servicio de ayuda y el personal de seguridad deben saber qué hacer en Defender para Office 365. Por ejemplo, si un usuario se queja de un mensaje que falta, ¿sabe su servicio de ayuda dónde o cómo buscarlo? Es probable que comprueben que están familiarizados con las herramientas del servicio de protección existente, pero ¿qué sucede con las herramientas de Defender para Office 365?

En cambio, si sigue los pasos de esta guía de migración, tendrá las siguientes ventajas tangibles para la migración:

- Interrupción mínima para los usuarios.
- Datos objetivos de Defender para Office 365 que puedes usar a medida que informas sobre el progreso y el éxito de la migración a la administración.
- Participación e instrucción tempranas para el personal de seguridad y el servicio de ayuda.

Cuanto más se familiarice con la forma en que Defender para Office 365 afectará a su organización, mejor será la transición para los usuarios, el personal de servicio de ayuda, el personal de seguridad y la administración.

Esta guía de migración le ofrece un plan para "girar gradualmente el marcado" para que pueda supervisar y probar cómo Defender for Office 365 afecta a los usuarios y su correo electrónico para que pueda reaccionar rápidamente ante los problemas que encuentre.

## <a name="the-migration-process"></a>Proceso de migración

El proceso de migración de un servicio de protección de terceros a Defender para Office 365 puede dividirse en tres fases, tal como se describe en la tabla siguiente:

:::image type="content" source="../../media/phase-diagrams/migration-phases.png" alt-text="Proceso de migración a Defender para Office 365" lightbox="../../media/phase-diagrams/migration-phases.png":::

|Fase|Descripción|
|---|---|
|[Preparar la migración](migrate-to-defender-for-office-365-prepare.md)|<ol><li>[Inventario de la configuración en el servicio de protección existente](migrate-to-defender-for-office-365-prepare.md#inventory-the-settings-at-your-existing-protection-service)</li><li>[Compruebe la configuración de protección existente en Microsoft 365](migrate-to-defender-for-office-365-prepare.md#check-your-existing-protection-configuration-in-microsoft-365)</li><li>[Comprobar la configuración de enrutamiento de correo](migrate-to-defender-for-office-365-prepare.md#check-your-mail-routing-configuration)</li><li>[Mover características que modifican mensajes a Microsoft 365](migrate-to-defender-for-office-365-prepare.md#move-features-that-modify-messages-into-microsoft-365)</li><li>[Definir experiencias de usuario masivo y correo no deseado](migrate-to-defender-for-office-365-prepare.md#define-spam-and-bulk-user-experiences)</li><li>[Identificar y designar cuentas de prioridad](migrate-to-defender-for-office-365-prepare.md#identify-and-designate-priority-accounts)</li></ol>|
|[Configurar Defender para Office 365](migrate-to-defender-for-office-365-setup.md)|<ol><li>[Crear grupos de distribución para usuarios piloto](migrate-to-defender-for-office-365-setup.md#step-1-create-distribution-groups-for-pilot-users)</li><li>[Configurar el envío de usuarios para informes de mensajes de usuario](migrate-to-defender-for-office-365-setup.md#step-2-configure-user-submission-for-user-message-reporting)</li><li>[Mantener o crear la regla de flujo de correo SCL=-1](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)</li><li>[Configurar filtrado mejorado para conectores](migrate-to-defender-for-office-365-setup.md#step-4-configure-enhanced-filtering-for-connectors)</li><li>[Crear directivas de protección piloto](migrate-to-defender-for-office-365-setup.md#step-5-create-pilot-protection-policies)</li></ol>|
|[Incorporación a Defender para Office 365](migrate-to-defender-for-office-365-onboard.md)|<ol><li>[Empezar a incorporar seguridad Teams](migrate-to-defender-for-office-365-onboard.md#step-1-begin-onboarding-security-teams)</li><li>[(Opcional) Eximir a los usuarios piloto del filtrado por el servicio de protección existente](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)</li><li>[Ajustar la inteligencia de suplantación](migrate-to-defender-for-office-365-onboard.md#step-3-tune-spoof-intelligence)</li><li>[Ajustar la protección de suplantación y la inteligencia de buzones](migrate-to-defender-for-office-365-onboard.md#step-4-tune-impersonation-protection-and-mailbox-intelligence)</li><li>[Usar datos de envíos de usuarios para medir y ajustar](migrate-to-defender-for-office-365-onboard.md#step-5-use-data-from-user-submissions-to-measure-and-adjust)</li><li>[(Opcional) Agregar más usuarios al piloto e iterar](migrate-to-defender-for-office-365-onboard.md#step-6-optional-add-more-users-to-your-pilot-and-iterate)</li><li>[Extender Microsoft 365 protección a todos los usuarios y desactivar la regla de flujo de correo SCL=-1](migrate-to-defender-for-office-365-onboard.md#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)</li><li>[Cambiar los registros MX](migrate-to-defender-for-office-365-onboard.md#step-8-switch-your-mx-records)</li></ol>|

## <a name="next-step"></a>Paso siguiente

- Continúe con [la fase 1: Preparar](migrate-to-defender-for-office-365-prepare.md).
