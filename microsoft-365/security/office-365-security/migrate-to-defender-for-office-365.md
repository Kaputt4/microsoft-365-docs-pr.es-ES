---
title: Migración de un servicio de protección de terceros a Microsoft Defender para Office 365
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
- m365solution-mdo-migration
ms.custom: ''
description: Obtenga información sobre la manera correcta de migrar desde dispositivos o servicios de protección de terceros como Google Postini, Barracuda Spam y Virus Firewall o Cisco IronPort para Microsoft Defender para Office 365 protección.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21194b32b394fec57f8055207ca3a840a2462ac8
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969450"
---
# <a name="migrate-from-a-third-party-protection-service-or-device-to-microsoft-defender-for-office-365"></a>Migración desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Si ya tiene un servicio o dispositivo de protección de terceros existente que se encuentra frente a Microsoft 365, puede usar esta guía para migrar la protección a Microsoft Defender para Office 365 para obtener las ventajas de una experiencia de administración consolidada, un costo potencialmente reducido (con productos que ya paga) y un producto maduro con protección de seguridad integrada. Para obtener más información, consulte [Microsoft Defender para Office 365](https://www.microsoft.com/security/business/threat-protection/office-365-defender).

Vea este breve vídeo para obtener más información sobre la migración a Defender para Office 365.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRwfH]

En esta guía se proporcionan pasos específicos y accionables para la migración y se asumen los siguientes hechos:

- Ya tiene buzones de Microsoft 365, pero actualmente usa un servicio o dispositivo de terceros para la protección de correo electrónico. El correo de Internet fluye a través del servicio de protección antes de la entrega a la organización de Microsoft 365 y la protección de Microsoft 365 es lo más baja posible (nunca está completamente desactivada; por ejemplo, siempre se aplica la protección contra malware).

  :::image type="content" source="../../media/mdo-migration-before.png" alt-text="El correo fluye desde Internet a través del servicio o dispositivo de protección de terceros antes de la entrega a Microsoft 365" lightbox="../../media/mdo-migration-before.png":::

- Está fuera de la fase de investigación y consideración para la protección por Defender para Office 365. Si necesita evaluar Defender para Office 365 para decidir si es adecuado para su organización, le recomendamos que tenga en cuenta las opciones descritas en [Probar Microsoft Defender para Office 365](try-microsoft-defender-for-office-365.md).

- Ya ha comprado licencias de Defender para Office 365.

- Debe retirar el servicio de protección de terceros existente, lo que significa que, en última instancia, deberá apuntar los registros MX de los dominios de correo electrónico a Microsoft 365. Cuando haya terminado, el correo de Internet fluirá directamente a Microsoft 365 y estará protegido exclusivamente por Exchange Online Protection (EOP) y Defender para Office 365.

  :::image type="content" source="../../media/mdo-migration-after.png" alt-text="El correo fluye desde Internet a Microsoft 365" lightbox="../../media/mdo-migration-after.png":::

Eliminar el servicio de protección existente en favor de Defender para Office 365 es un gran paso que no debe tomar a la ligera, ni debe apresurarse a realizar el cambio. Las instrucciones de esta guía de migración le ayudarán a realizar la transición de la protección de forma ordenada con una interrupción mínima para los usuarios.

Los pasos de migración de alto nivel se muestran en el diagrama siguiente. Los pasos reales se enumeran en la sección denominada [El proceso de migración](#the-migration-process) más adelante en este artículo.

:::image type="content" source="../../media/mdo-migration-overview.png" alt-text="El proceso de migración desde un dispositivo o solución de protección de terceros a Defender para Office 365" lightbox="../../media/mdo-migration-overview.png":::

## <a name="why-use-the-steps-in-this-guide"></a>¿Por qué usar los pasos de esta guía?

En el sector de TI, las sorpresas suelen ser malas. Simplemente voltear los registros MX para que apunten a Microsoft 365 sin pruebas previas y cuidadosas dará lugar a muchas sorpresas. Por ejemplo:

- Es probable que usted o sus predecesores hayan dedicado mucho tiempo y esfuerzo a personalizar el servicio de protección existente para una entrega de correo óptima (es decir, bloquear lo que debe bloquearse y permitir lo que se debe permitir). Es casi una certeza garantizada que no todas las personalizaciones del servicio de protección actual son necesarias en Defender para Office 365. También es muy posible que Defender para Office 365 presente nuevos problemas (permite o bloquea) que no se han podido producir o que no eran necesarios en el servicio de protección actual.
- El departamento de soporte técnico y el personal de seguridad deben saber qué hacer en Defender para Office 365. Por ejemplo, si un usuario se queja de que falta un mensaje, ¿sabe el departamento de soporte técnico dónde o cómo buscarlo? Es probable que estén familiarizados con las herramientas del servicio de protección existente, pero ¿qué ocurre con las herramientas de Defender para Office 365?

Por el contrario, si sigue los pasos de esta guía de migración, obtendrá las siguientes ventajas tangibles para la migración:

- Interrupción mínima para los usuarios.
- Datos objetivos de Defender para Office 365 que puede usar para informar sobre el progreso y el éxito de la migración a la administración.
- Participación temprana e instrucción para el departamento de soporte técnico y el personal de seguridad.

Cuanto más se familiarice con cómo afectará Defender para Office 365 a su organización, mejor será la transición para los usuarios, el personal del departamento de soporte técnico, el personal de seguridad y la administración.

Esta guía de migración le ofrece un plan para "activar el marcado" gradualmente para que pueda supervisar y probar cómo afecta Defender para Office 365 a los usuarios y su correo electrónico para que pueda reaccionar rápidamente ante cualquier problema que encuentre.

## <a name="the-migration-process"></a>El proceso de migración

El proceso de migración de un servicio de protección de terceros a Defender para Office 365 se puede dividir en tres fases, como se describe en la tabla siguiente:

:::image type="content" source="../../media/phase-diagrams/migration-phases.png" alt-text="Proceso para migrar a Defender para Office 365" lightbox="../../media/phase-diagrams/migration-phases.png":::

|Fase|Descripción|
|---|---|
|[Preparación para la migración](migrate-to-defender-for-office-365-prepare.md)|<ol><li>[Inventario de la configuración en el servicio de protección existente](migrate-to-defender-for-office-365-prepare.md#inventory-the-settings-at-your-existing-protection-service)</li><li>[Comprobación de la configuración de protección existente en Microsoft 365](migrate-to-defender-for-office-365-prepare.md#check-your-existing-protection-configuration-in-microsoft-365)</li><li>[Comprobación de la configuración de enrutamiento de correo](migrate-to-defender-for-office-365-prepare.md#check-your-mail-routing-configuration)</li><li>[Traslado de características que modifican mensajes a Microsoft 365](migrate-to-defender-for-office-365-prepare.md#move-features-that-modify-messages-into-microsoft-365)</li><li>[Definición de experiencias de usuario masivas y de correo no deseado](migrate-to-defender-for-office-365-prepare.md#define-spam-and-bulk-user-experiences)</li><li>[Identificación y designación de cuentas prioritarias](migrate-to-defender-for-office-365-prepare.md#identify-and-designate-priority-accounts)</li></ol>|
|[Configuración de Defender para Office 365](migrate-to-defender-for-office-365-setup.md)|<ol><li>[Creación de grupos de distribución para usuarios piloto](migrate-to-defender-for-office-365-setup.md#step-1-create-distribution-groups-for-pilot-users)</li><li>[Configuración del envío de usuarios para informes de mensajes de usuario](migrate-to-defender-for-office-365-setup.md#step-2-configure-user-submission-for-user-message-reporting)</li><li>[Mantener o crear la regla de flujo de correo SCL=-1](migrate-to-defender-for-office-365-setup.md#step-3-maintain-or-create-the-scl-1-mail-flow-rule)</li><li>[Configuración del filtrado mejorado para conectores](migrate-to-defender-for-office-365-setup.md#step-4-configure-enhanced-filtering-for-connectors)</li><li>[Creación de directivas de protección piloto](migrate-to-defender-for-office-365-setup.md#step-5-create-pilot-protection-policies)</li></ol>|
|[Incorporación a Defender para Office 365](migrate-to-defender-for-office-365-onboard.md)|<ol><li>[Inicio de la incorporación de Security Teams](migrate-to-defender-for-office-365-onboard.md#step-1-begin-onboarding-security-teams)</li><li>[(Opcional) Eximir a los usuarios piloto del filtrado por el servicio de protección existente](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service)</li><li>[Optimizar la inteligencia de suplantación de identidad](migrate-to-defender-for-office-365-onboard.md#step-3-tune-spoof-intelligence)</li><li>[Optimización de la protección de suplantación y la inteligencia de buzones](migrate-to-defender-for-office-365-onboard.md#step-4-tune-impersonation-protection-and-mailbox-intelligence)</li><li>[Uso de datos de envíos de usuarios para medir y ajustar](migrate-to-defender-for-office-365-onboard.md#step-5-use-data-from-user-submissions-to-measure-and-adjust)</li><li>[(Opcional) Agregar más usuarios al piloto e iterar](migrate-to-defender-for-office-365-onboard.md#step-6-optional-add-more-users-to-your-pilot-and-iterate)</li><li>[Ampliar la protección de Microsoft 365 a todos los usuarios y desactivar la regla de flujo de correo SCL=-1](migrate-to-defender-for-office-365-onboard.md#step-7-extend-microsoft-365-protection-to-all-users-and-turn-off-the-scl-1-mail-flow-rule)</li><li>[Cambiar los registros MX](migrate-to-defender-for-office-365-onboard.md#step-8-switch-your-mx-records)</li></ol>|

## <a name="next-step"></a>Paso siguiente

- Continúe con [la fase 1: Preparar](migrate-to-defender-for-office-365-prepare.md).
