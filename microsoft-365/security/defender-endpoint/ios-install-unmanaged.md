---
title: Implementar Microsoft Defender para endpoint en características de iOS
description: Describe cómo implementar Microsoft Defender para Endpoint en dispositivos iOS no inscritos.
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, configure, features, ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8ea5e2c5efef1becf69f0d5f7e46b57aa89ef94a
ms.sourcegitcommit: e685fafd6dde4901c378685b423883faed7b4fe7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2021
ms.locfileid: "59460285"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>Implementar Microsoft Defender para endpoint en dispositivos iOS no inscritos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Defender para endpoint en iOS usa una VPN para proporcionar la característica de protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>Configurar Microsoft Defender para señales de riesgo de extremo en la directiva de protección de aplicaciones (MAM)

Microsoft Defender para endpoint se puede configurar para enviar señales de amenaza que se usarán en las directivas de protección de aplicaciones (APP, también conocidas como MAM) en iOS/iPadOS. Con esta funcionalidad, también puedes usar Microsoft Defender para Endpoint para proteger el acceso a datos corporativos desde dispositivos no inscritos.

### <a name="pre-requisites"></a>Requisitos previos

1. **Compruebe que el conector está habilitado.** <br> En la [consola de seguridad unificada,](https://security.microsoft.com)vaya **a Configuración**  >  **Endpoints**  >  **Advanced Features** y asegúrese de que Microsoft Intune **conexión** está habilitada.
2. **Veerify que el conector está habilitado en el portal de Intune**. <br> En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Endpoint **Security** Microsoft Defender para Endpoint y asegúrese de que el estado de conexión está  >   habilitado.

Siga estos pasos para configurar directivas de protección de aplicaciones con Microsoft Defender para endpoint:

1. Configure la conexión desde el espacio empresarial Microsoft Endpoint Manager a Microsoft Defender para Endpoint. En el Centro de administración  de [Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Conectores de administración de inquilinos y tokens de Microsoft Defender para Endpoint (en Plataforma cruzada) o Endpoint Security Microsoft Defender para Endpoint \>  \>   \>  (en Configuración) y active los alternancias en Directiva de protección de **aplicaciones Configuración para iOS**.
1. Seleccione **Guardar**. Debería ver que **el estado de** conexión ahora está establecido en **Habilitado**.
1. Crear la directiva de protección de aplicaciones: una vez completada la configuración del conector de Microsoft Defender para puntos de conexión, vaya a **Directivas** de protección de aplicaciones \>  (en Directiva) para crear una nueva directiva o actualizar una existente.
1. Seleccione la plataforma, **Aplicaciones, Protección de datos, Configuración** de requisitos de Acceso que su organización requiere para la directiva.
1. En **Condiciones del** dispositivo de inicio \> **condicional,** encontrarás la configuración Nivel máximo de amenaza del dispositivo **permitido.** Esto debe configurarse en Low, Medium, High o Secured. Las acciones disponibles serán Bloquear acceso **o** **Borrar datos**. Es posible que vea un cuadro de diálogo informativo para asegurarse de que el conector está configurado antes de que esta configuración suba a efecto. Si el conector ya está configurado, puede omitir este cuadro de diálogo.
1. Termina con Asignaciones y guarda la directiva.

Para obtener más información sobre mam o directiva de protección de aplicaciones, consulta configuración de la directiva de protección [de aplicaciones de iOS](/mem/intune/apps/app-protection-policy-settings-ios).

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Implementar Microsoft Defender para endpoint para MAM o en dispositivos no inscritos

Microsoft Defender para endpoint en iOS habilita el escenario de directiva de protección de aplicaciones y está disponible en la Tienda de aplicaciones de Apple.

Cuando las directivas de protección de aplicaciones están configuradas para que las aplicaciones incluyan señales de riesgo de dispositivos de Microsoft Defender para Endpoint, los usuarios se redirigirán para instalar Microsoft Defender para Endpoint al usar dichas aplicaciones. Como alternativa, los usuarios también pueden instalar la versión más reciente de la aplicación directamente desde la Tienda de aplicaciones de Apple.
