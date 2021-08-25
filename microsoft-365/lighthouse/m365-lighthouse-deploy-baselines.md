---
title: Implementar Microsoft 365 Lighthouse base
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo implementar Microsoft 365 Lighthouse líneas base.
ms.openlocfilehash: 62fc9afcbf10a0cd77c2fe2d2f7140b5197dd42a
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "58507907"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Implementar Microsoft 365 Lighthouse base 

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse línea base le permiten implementar configuraciones de inquilino administrado estándar para proteger usuarios, dispositivos y datos dentro de los inquilinos del cliente. Hay seis configuraciones de línea base predeterminadas que vienen estándar con Lighthouse:

- Requerir MFA para administradores
- Requerir MFA para usuarios finales
- Bloquear autenticación heredada
- Configurar la inscripción de dispositivos en Microsoft Endpoint Manager: unión a Azure AD
- Configurar la directiva antivirus de Defender para Windows dispositivos
- Configurar la directiva de cumplimiento para Windows dispositivos

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que usted y sus inquilinos de clientes cumplan los requisitos enumerados en [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

## <a name="learn-more-about-the-default-baseline"></a>Más información sobre la línea base predeterminada

Seleccione **Líneas base en** el panel de navegación izquierdo para abrir la página Líneas base. Verá que la línea base predeterminada ya se ha agregado al grupo de inquilinos predeterminado (todos los inquilinos). Para ver las configuraciones de línea base predeterminadas, seleccione **Ver línea base** para abrir la página Línea base predeterminada. Las configuraciones se enumeran como pasos de implementación. Seleccione cualquiera de los pasos de implementación para ver los detalles de implementación y el impacto del usuario.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Captura de pantalla de la página de línea base predeterminada.>.":::

## <a name="deploy-a-baseline-configuration"></a>Implementar una configuración de línea base  

1. En la página de navegación izquierda, seleccione **Inquilinos** para ver una lista de los inquilinos incorporados.

2. Seleccione el espacio empresarial en el que desea implementar la configuración de línea base.

3. Seleccione la **pestaña Planes de** implementación para ver todos los pasos de implementación de la línea base que se han agregado al plan de implementación del inquilino.

4. Seleccione un paso de implementación para abrir la página de pasos de implementación.

5. Seleccione **Aplicar** para aplicar el paso de implementación seleccionado al espacio empresarial. Si el paso de implementación indica "Esta acción requiere un paso manual", asegúrese de completar el paso manual para que el paso de implementación se aplique correctamente.

## <a name="related-content"></a>Contenido relacionado

[Introducción al uso de líneas base para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)