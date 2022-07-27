---
title: Convertirse en socio de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre los pasos y requisitos para integrar la solución con Microsoft Defender para punto de conexión y ser asociado
keywords: partner, integration, solution validation, certification, requirements, member, misa, application portal
ms.prod: m365-security
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
ms.openlocfilehash: 276f411699f4a9db61850a04da3ff18d3c6bb2a7
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051214"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Convertirse en socio de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Para convertirse en un asociado de solución de Defender para punto de conexión, deberá seguir y completar los pasos siguientes.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-license"></a>Paso 1: Suscribirse a una licencia de Microsoft Defender para punto de conexión

¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una evaluación gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink) La suscripción le permite usar un inquilino de Microsoft Defender para punto de conexión con hasta tres dispositivos para desarrollar soluciones que se integren con Microsoft Defender para punto de conexión.

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Paso 2: Cumplir los requisitos de validación y certificación de la solución

La mejor manera de que los asociados tecnológicos certifiquen que su integración funciona es hacer que un cliente conjunto apruebe el diseño de integración sugerido (el cliente puede usar la opción \(**Recomendar un asociado** Asociados y API > Aplicaciones\) de asociados en la [página Aplicación de asociados](https://security.microsoft.com/interoperability/partnersapps) de la Microsoft 365 Defender y hacer que se pruebe y disminución de nivel a la Microsoft Defender para punto de conexión equipo.

Una vez que el equipo de Microsoft Defender para punto de conexión haya revisado y aprobado la integración, le indicaremos que se incluya como asociado en la Asociación de seguridad inteligente de Microsoft.

## <a name="step-3-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Paso 3: Aparece en el portal de aplicaciones de Microsoft Defender para punto de conexión asociado

Microsoft Defender para punto de conexión admite la detección e integración de aplicaciones de terceros mediante la [página de asociados](partner-applications.md) del producto que se inserta en el portal de administración de Microsoft Defender para punto de conexión.

Para que su empresa aparezca como partner en la página del asociado en el producto, deberá proporcionar la siguiente información:

1. Logotipo cuadrado (SVG).
2. Nombre del producto que se va a presentar.
3. Proporcione una descripción del producto de 15 palabras.
4. Vínculo a la página de aterrizaje para que el cliente complete la entrada de integración o blog que incluirá suficiente información para los clientes. Cualquier comunicado de prensa, incluido el nombre del producto Microsoft Defender para punto de conexión, debe ser revisado por los equipos de marketing e ingeniería. Espere al menos 10 días para que se realice el proceso de revisión.
5. Si usa un enfoque de Azure AD multiinquilino, necesitaremos el nombre de la aplicación de Azure AD para realizar un seguimiento del uso de la aplicación.
6. Incluya el campo User-Agent en cada llamada API realizada a Microsoft Defender para punto de conexión conjunto público de API o API de Graph Security. Esto se usará con fines estadísticos, solución de problemas y reconocimiento de asociados. Además, este paso es un requisito para la pertenencia a Microsoft Intelligent Security Association (MISA).

   Siga estos pasos:

   - Establezca el campo User-Agent de cada encabezado de solicitud HTTP en el formato siguiente.

     ```http
     MdePartner-{CompanyName}-{ProductName}/{Version}
     ```

     Por ejemplo, User-Agent:

     ```http
     MdePartner-Contoso-ContosoCognito/1.0.0
     ```

   - Para obtener más información, consulte [la sección 14.43 de RFC 2616](https://tools.ietf.org/html/rfc2616#section-14.43).

Las asociaciones con Microsoft Defender para punto de conexión ayudan a nuestros clientes mutuos a optimizar aún más, integrar y orquestar las defensas. Nos complace que haya elegido convertirse en un partner Microsoft Defender para punto de conexión y lograr nuestro objetivo común de proteger eficazmente a los clientes y sus activos mediante la prevención y la respuesta a las amenazas modernas juntos.

## <a name="misa-nomination"></a>Nominación de MISA 
Los proveedores de servicios de seguridad administrados (MSSP) y los proveedores de software independientes (ISV) se pueden nominar a microsoft Intelligent Security Association (MISA). Para obtener más información, consulte [la página de información misa](https://www.microsoft.com/security/business/intelligent-security-association).


## <a name="related-topics"></a>Temas relacionados

- [Oportunidades para asociados técnicos](partner-integration.md)
