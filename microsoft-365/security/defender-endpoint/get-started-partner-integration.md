---
title: Convertirse en socio de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre los pasos y los requisitos para integrar la solución con Microsoft Defender para endpoint y ser socio
keywords: partner, integration, solution validation, certification, requirements, member, misa, application portal
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 35ba1fe85fa9b62770142636d46303b37534b976
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893322"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Convertirse en socio de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Para convertirse en un partner de soluciones de Defender for Endpoint, deberá seguir y completar los siguientes pasos.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>Paso 1: Suscribirse a una licencia de Microsoft Defender para endpoint developer
Suscribirse a la [licencia de Microsoft Defender para Endpoint Developer](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9). Suscribirte te permite usar un inquilino de Microsoft Defender para endpoint con hasta 10 dispositivos para desarrollar soluciones que se integren con Microsoft Defender para Endpoint. 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Paso 2: Cumplir los requisitos de validación y certificación de la solución
La mejor manera de que los partners tecnológicos certifiquen que su integración funciona es que un [](https://securitycenter.microsoft.com/interoperability/partners) cliente conjunto apruebe el diseño de integración sugerido (el cliente puede usar la opción Recomendar **un** partner en la página Aplicación de partners en el Centro de seguridad de Microsoft Defender) y hacer que se prueba y se degrada al equipo de Microsoft Defender para endpoints.

Una vez que el equipo de Microsoft Defender para endpoint haya revisado y aprobado la integración, le dirigiremos a que se le incluya como socio en la Asociación de seguridad inteligente de Microsoft.

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>Paso 3: Convertirse en miembro de la Asociación de seguridad inteligente de Microsoft
[Microsoft Intelligent Security Association](https://www.microsoft.com/security/partnerships/intelligent-security-association) es un programa específicamente para los socios de seguridad de Microsoft para ayudar a enriquecer sus productos de seguridad y mejorar la capacidad de descubrimiento de los clientes de sus integraciones en los productos de seguridad de Microsoft.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Paso 4: Obtener una lista en el portal de aplicaciones de partners de Microsoft Defender para endpoint
Microsoft Defender para endpoint admite la detección e [](partner-applications.md) integración de aplicaciones de terceros mediante la página de partners del producto que está incrustada en el portal de administración de Microsoft Defender para endpoints. 

Para que su empresa aparezca como partner en la página de partners del producto, deberá proporcionar la siguiente información:

1. Logotipo cuadrado (SVG).
2. Nombre del producto que se va a presentar.
3. Proporcione una descripción del producto de 15 palabras.
4. Vínculo a la página de aterrizaje para que el cliente complete la entrada de integración o blog que incluirá información suficiente para los clientes. Los equipos de marketing e ingeniería deben revisar cualquier nota de prensa, incluido el nombre del producto de Microsoft Defender para endpoint. Espere al menos 10 días para que se haga el proceso de revisión.
5.  Si usa un enfoque de Azure AD multiinquilino, necesitará el nombre de la aplicación de Azure AD para realizar un seguimiento del uso de la aplicación.
6. Incluya el User-Agent en cada llamada api realizada a Microsoft Defender para el conjunto público endpoint de API o Graph API de seguridad. Esto se usará con fines estadísticos, solución de problemas y reconocimiento de partners. Además, este paso es un requisito para pertenecer a Microsoft Intelligent Security Association (MISA).

    Siga estos pasos:
    
    - Establezca el User-Agent campo de cada encabezado de solicitud HTTP en el siguiente formato.

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - Por ejemplo, User-Agent: `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - Para obtener más información, [vea RFC 2616 section-14.43](https://tools.ietf.org/html/rfc2616#section-14.43).

Las asociaciones con Microsoft Defender para Endpoint ayudan a nuestros clientes mutuos a simplificar, integrar y orquestar las defensas. Nos complace que haya elegido convertirse en un partner de Microsoft Defender para endpoints y lograr nuestro objetivo común de proteger eficazmente a los clientes y sus activos al impedir y responder juntos a las amenazas modernas.

## <a name="related-topics"></a>Temas relacionados
- [Oportunidades para asociados técnicos](partner-integration.md)
