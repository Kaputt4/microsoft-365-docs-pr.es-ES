---
title: Implementación de Microsoft Defender para punto de conexión en características de iOS
description: Describe cómo implementar Microsoft Defender para punto de conexión en dispositivos iOS no inscritos.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, ios, configure, features, ios
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 71638b0d0ac72d9e8b4be984cf23be6933acb0d4
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222856"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>Implementación de Microsoft Defender para punto de conexión en dispositivos iOS no inscritos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Defender para punto de conexión en iOS usa una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo.

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>Configuración de señales de riesgo Microsoft Defender para punto de conexión en la directiva de protección de aplicaciones (MAM)

Microsoft Defender para punto de conexión en iOS, que ya protege a los usuarios empresariales en escenarios de Mobile Administración de dispositivos (MDM), ahora amplía la compatibilidad con Mobile App Management (MAM) para los dispositivos que no están inscritos mediante Intune administración de dispositivos móviles (MDM). También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras siguen usando Intune para la administración de aplicaciones móviles (MAM). Esta funcionalidad le permite administrar y proteger los datos de su organización dentro de una aplicación.

Microsoft Defender para punto de conexión en la información de amenazas de iOS se aprovecha Intune directivas de Protección de aplicaciones para proteger estas aplicaciones. Las directivas de protección de aplicaciones (APP) que garantizan los datos de la organización siguen siendo seguras o se encuentran en una aplicación administrada. Una aplicación administrada tiene directivas de protección de aplicaciones aplicadas y se puede administrar mediante Intune.  

Microsoft Defender para punto de conexión en iOS admite ambas configuraciones de MAM
- **Intune MDM + MAM**: los administradores de TI solo pueden administrar aplicaciones mediante directivas de protección de aplicaciones en dispositivos inscritos con Intune administración de dispositivos móviles (MDM).
- **MAM sin inscripción de dispositivos**: MAM sin inscripción de dispositivos, o MAM-WE, permite a los administradores de TI administrar aplicaciones mediante [directivas de protección](/mem/intune/apps/app-protection-policy) de aplicaciones en dispositivos no inscritos con Intune MDM. Esto significa que las aplicaciones pueden administrarse mediante Intune en dispositivos inscritos con proveedores de EMM de terceros. Para administrar aplicaciones mediante ambas configuraciones anteriores, los clientes deben usar Intune en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)

Para habilitar esta funcionalidad, un administrador debe configurar la conexión entre Microsoft Defender para punto de conexión y Intune, crear la directiva de protección de aplicaciones y aplicar la directiva en aplicaciones y dispositivos de destino. 
 
Los usuarios finales también deben realizar pasos para instalar Microsoft Defender para punto de conexión en su dispositivo y activar el flujo de incorporación.

### <a name="pre-requisites"></a>Requisitos previos

1. **Compruebe que el conector está habilitado**. <br> En la [consola de seguridad unificada](https://security.microsoft.com), vaya a **Configuración** > **Puntos de conexión****Características avanzadas** >  y asegúrese de que **Microsoft Intune conexión** está habilitada.

  :::image type="content" source="images/enable-intune-connection.png" alt-text="El conector de Defender para punto de conexión: Intune" lightbox="images/enable-intune-connection.png":::

  
2. **Compruebe que el conector está habilitado en el portal de Intune**. <br> En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Seguridad** >  de punto de conexión **Microsoft Defender para punto de conexión** y asegúrese de que el estado de conexión está habilitado.

  :::image type="content" source="images/app-settings.png" alt-text="La configuración de la aplicación" lightbox="images/app-settings.png":::

### <a name="create-an-app-protection-policy"></a>Crear una directiva de protección de aplicaciones
 
Bloquee el acceso o borre los datos de una aplicación administrada en función de Microsoft Defender para punto de conexión señales de riesgo mediante la creación de una directiva de protección de aplicaciones.
Microsoft Defender para punto de conexión se puede configurar para enviar señales de amenaza que se usarán en las directivas de protección de aplicaciones (APP, también conocida como MAM). Con esta funcionalidad, puede usar Microsoft Defender para punto de conexión para proteger las aplicaciones administradas.

1. Crear una directiva <br>
Las directivas de protección de aplicaciones (APP) que garantizan los datos de la organización siguen siendo seguras o se encuentran en una aplicación administrada. Una directiva puede ser una regla que se aplica cuando el usuario intenta acceder o mover datos "corporativos", o un conjunto de acciones que se prohíben o supervisan cuando el usuario está dentro de la aplicación. 

:::image type="content" source="images/create-policy.png" alt-text="Pestaña Crear directiva en el elemento de menú Directivas de Protección de aplicaciones" lightbox="images/create-policy.png":::

2. Agregar aplicaciones <br>
    a. Elija cómo desea aplicar esta directiva a las aplicaciones de distintos dispositivos. A continuación, agregue al menos una aplicación. <br>
    Use esta opción para especificar si esta directiva se aplica a dispositivos no administrados. También puede elegir dirigir la directiva a aplicaciones en dispositivos de cualquier estado de administración.
Debido a que la administración de aplicaciones móviles no requiere la administración de dispositivos, puede proteger los datos de la empresa en dispositivos administrados y no administrados. La administración se centra en la identidad del usuario, lo que elimina la necesidad de administrar dispositivos. Las empresas pueden usar directivas de protección de aplicaciones con o sin MDM al mismo tiempo. Por ejemplo, piense el caso de un empleado que utiliza tanto un teléfono proporcionado por la empresa como su propia tableta personal. El teléfono de la empresa está inscrito en MDM y protegido por directivas de protección de aplicaciones, mientras que el dispositivo personal está protegido únicamente por directivas de protección de aplicaciones.

    b. Seleccionar aplicaciones<br>
    Una aplicación administrada es aquella que tiene las directivas de protección de aplicaciones aplicadas y puede administrarse mediante Intune. Cualquier aplicación que se haya integrado con el [SDK de Intune](/mem/intune/developer/app-sdk) o que esté encapsulada por el [Intune App Wrapping Tool](/mem/intune/developer/apps-prepare-mobile-application-management) se puede administrar mediante Intune directivas de protección de aplicaciones. Consulte la lista oficial de [aplicaciones protegidas de Microsoft Intune](/mem/intune/apps/apps-supported-intune-apps) que se han creado con estas herramientas y están disponibles para uso público.

    *Ejemplo: Outlook como una aplicación administrada*

     :::image type="content" source="images/managed-app.png" alt-text="Elemento de menú de Microsoft Outlook en el panel de navegación izquierdo" lightbox="images/managed-app.png":::
  

 3. Establezca los requisitos de seguridad de inicio de sesión para la directiva de protección. <br>
Seleccione **Establecer > nivel máximo de amenaza de dispositivo permitido** en **Condiciones del dispositivo** y escriba un valor. A continuación, seleccione  **Acción: "Bloquear acceso"**. Microsoft Defender para punto de conexión en iOS comparte este nivel de amenaza de dispositivo.

    
   :::image type="content" source="images/conditional-launch.png" alt-text="Panel Condiciones del dispositivo" lightbox="images/conditional-launch.png":::

4. Asigne grupos de usuarios a los que se debe aplicar la directiva.<br>
  Seleccione **Grupos incluidos**. A continuación, agregue los grupos pertinentes. 


Para obtener más información sobre mam o directiva de protección de aplicaciones, consulte configuración de directivas de [protección de aplicaciones de iOS](/mem/intune/apps/app-protection-policy-settings-ios).

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Implementación de Microsoft Defender para punto de conexión para MAM o en dispositivos no inscritos

Microsoft Defender para punto de conexión en iOS habilita el escenario de directiva de protección de aplicaciones y está disponible en la Tienda de aplicaciones de Apple.

Cuando las directivas de protección de aplicaciones están configuradas para que las aplicaciones incluyan señales de riesgo de dispositivo de Microsoft Defender para punto de conexión, se redirigirá a los usuarios para instalar Microsoft Defender para punto de conexión al usar dichas aplicaciones. Como alternativa, los usuarios también pueden instalar la versión más reciente de la aplicación directamente desde la tienda de aplicaciones de Apple.
