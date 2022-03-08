---
title: Convertirse en socio de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre los pasos y los requisitos para integrar la solución con Microsoft Defender para endpoint y ser socio
keywords: partner, integration, solution validation, certification, requirements, member, misa, application portal
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: b063d8435817d7dd64c3febf6e3399f3876ef894
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319831"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Convertirse en socio de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Para convertirse en un partner de soluciones de Defender for Endpoint, deberá seguir y completar los siguientes pasos.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-license"></a>Paso 1: Suscribirse a una licencia de Microsoft Defender para endpoint

¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink). Suscribirte te permite usar un inquilino de Microsoft Defender para endpoint con hasta tres dispositivos para desarrollar soluciones que se integren con Microsoft Defender para Endpoint.

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Paso 2: Cumplir los requisitos de validación y certificación de la solución

La mejor manera de que los partners tecnológicos certifiquen que su integración funciona es que un cliente conjunto apruebe el diseño de integración sugerido  (\(el cliente puede usar la opción Recomendar un partner Partners y api > [](https://security.microsoft.com/interoperability/partnersapps) Aplicaciones\) de partners en la página Aplicación de partners del Microsoft 365 Defender y hacer que se probara y se demostrase en el equipo de Microsoft Defender para endpoints.

Una vez que el equipo de Microsoft Defender para endpoint haya revisado y aprobado la integración, le dirigiremos a que se le incluya como socio en la Asociación de seguridad inteligente de Microsoft.

## <a name="step-3-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Paso 3: Obtener una lista en el portal de aplicaciones de partners de Microsoft Defender para endpoint

Microsoft Defender para endpoint admite la detección e integración de aplicaciones de terceros mediante la [](partner-applications.md) página de partners del producto que está incrustada en el portal de administración de Microsoft Defender para endpoints.

Para que su empresa aparezca como partner en la página de partners del producto, deberá proporcionar la siguiente información:

1. Logotipo cuadrado (SVG).
2. Nombre del producto que se va a presentar.
3. Proporcione una descripción del producto de 15 palabras.
4. Vínculo a la página de aterrizaje para que el cliente complete la entrada de integración o blog que incluirá información suficiente para los clientes. Los equipos de marketing e ingeniería deben revisar cualquier nota de prensa, incluido el nombre del producto de Microsoft Defender para endpoint. Espere al menos 10 días para que se haga el proceso de revisión.
5. Si usa un enfoque de Azure AD multiinquilino, necesitamos el nombre Azure AD aplicación para realizar un seguimiento del uso de la aplicación.
6. Incluya el User-Agent en cada llamada a la API realizada a Microsoft Defender para el conjunto público endpoint de API o Graph API de seguridad. Esto se usará con fines estadísticos, solución de problemas y reconocimiento de partners. Además, este paso es un requisito para pertenecer a Microsoft Intelligent Security Association (MISA).

   Siga estos pasos:

   - Establezca el User-Agent campo de cada encabezado de solicitud HTTP en el siguiente formato.

     ```http
     MdePartner-{CompanyName}-{ProductName}/{Version}
     ```

     Por ejemplo, User-Agent:

     ```http
     MdePartner-Contoso-ContosoCognito/1.0.0
     ```

   - Para obtener más información, [vea RFC 2616 section-14.43](https://tools.ietf.org/html/rfc2616#section-14.43).

Las asociaciones con Microsoft Defender para Endpoint ayudan a nuestros clientes mutuos a simplificar, integrar y orquestar las defensas. Nos complace que haya elegido convertirse en un partner de Microsoft Defender para endpoints y lograr nuestro objetivo común de proteger eficazmente a los clientes y sus activos al impedir y responder juntos a las amenazas modernas.

## <a name="misa-nomination"></a>Nominación misa 
Los proveedores de servicios de seguridad administrados (MSSP) y los proveedores de software independientes (ISV) se pueden nominar a la Asociación de seguridad inteligente de Microsoft (MISA). Para obtener más información, vea [la página de información de MISA](https://www.microsoft.com/security/business/intelligent-security-association).


## <a name="related-topics"></a>Temas relacionados

- [Oportunidades para asociados técnicos](partner-integration.md)
