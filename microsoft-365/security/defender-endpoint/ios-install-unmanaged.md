---
title: Implementar Microsoft Defender para endpoint en características de iOS
description: Describe cómo implementar Microsoft Defender para Endpoint en dispositivos iOS no inscritos.
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, configure, features, ios
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f5743cecab5e6a1bd0ab51b5a984a49e04f80184
ms.sourcegitcommit: 1e990628d72b6d392500ea564859543e7c8bc632
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "60386213"
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

Microsoft Defender para Endpoint en Android, que ya protege a los usuarios empresariales en escenarios de administración de dispositivos móviles (MDM), ahora amplía la compatibilidad con Mobile App Management (MAM), para dispositivos que no están inscritos con la administración de dispositivos móviles (MDM) de Intune. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras que sigue usando Intune para la administración de aplicaciones móviles (MAM). Esta funcionalidad le permite administrar y proteger los datos de su organización dentro de una aplicación.

Las directivas de Protección de aplicaciones de Intune aprovechan la información de las amenazas de Microsoft Defender para Endpoint en Android para proteger estas aplicaciones. Las directivas de protección de aplicaciones (APP) son reglas que garantizan que los datos de una organización permanecen seguros o contenidos en una aplicación administrada. Una aplicación administrada tiene directivas de protección de aplicaciones aplicadas a ella y Intune puede administrarla.  

Microsoft Defender para Endpoint en Android admite ambas configuraciones de MAM
- **MDM y MAM** de Intune: los administradores de TI solo pueden administrar aplicaciones con directivas de protección de aplicaciones en dispositivos inscritos con la administración de dispositivos móviles (MDM) de Intune.
- **MAM sin inscripción de dispositivos:** MAM sin inscripción de dispositivos, [](/mem/intune/app/app-protection-policy) o MAM-WE, permite a los administradores de TI administrar aplicaciones mediante directivas de protección de aplicaciones en dispositivos que no están inscritos con MDM de Intune. Esto significa que Intune puede administrar aplicaciones en dispositivos inscritos con proveedores de EMM de terceros. Para administrar las aplicaciones que usan en ambas configuraciones anteriores, los clientes deben usar Intune en el [centro de administración Microsoft Endpoint Manager administración](https://go.microsoft.com/fwlink/?linkid=2109431)

Para habilitar esta funcionalidad, un administrador debe configurar la conexión entre Microsoft Defender para Endpoint e Intune, crear la directiva de protección de aplicaciones y aplicar la directiva en dispositivos y aplicaciones de destino. 
 
Los usuarios finales también deben tomar medidas para instalar Microsoft Defender para Endpoint en su dispositivo y activar el flujo de incorporación.

### <a name="pre-requisites"></a>Requisitos previos

1. **Compruebe que el conector está habilitado.** <br> En la [consola de seguridad unificada,](https://security.microsoft.com)vaya **a Configuración**  >  **Endpoints**  >  **Advanced Features** y asegúrese de que Microsoft Intune **conexión** está habilitada.

  ![Imagen de Defender para endpoint -Intune connector](images/enable-intune-connection.png)
  
2. **Compruebe que el conector está habilitado en el portal de Intune**. <br> En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Endpoint **Security** Microsoft Defender para Endpoint y asegúrese de que el estado de conexión está  >   habilitado.

  ![Configuración de la aplicación](images/app-settings.png)

### <a name="create-an-app-protection-policy"></a>Crear una directiva de protección de aplicaciones
 
Bloquear el acceso o borrar datos de una aplicación administrada basada en señales de riesgo de Microsoft Defender para puntos de conexión mediante la creación de una directiva de protección de aplicaciones.
Microsoft Defender para endpoint se puede configurar para enviar señales de amenaza que se usarán en las directivas de protección de aplicaciones (APP, también conocidas como MAM). Con esta funcionalidad, puedes usar Microsoft Defender para Endpoint para proteger las aplicaciones administradas.

1. Crear una directiva <br>
Las directivas de protección de aplicaciones (APP) son reglas que garantizan que los datos de una organización permanecen seguros o contenidos en una aplicación administrada. Una directiva puede ser una regla que se aplica cuando el usuario intenta acceder o mover datos "corporativos", o un conjunto de acciones que están prohibidas o supervisadas cuando el usuario está dentro de la aplicación. 

![Imagen de creación de directivas](images/create-policy.png)

2. Agregar aplicaciones <br>
    a. Elige cómo quieres aplicar esta directiva a aplicaciones en diferentes dispositivos. A continuación, agrega al menos una aplicación. <br>
    Use esta opción para especificar si esta directiva se aplica a dispositivos no administrados. También puedes elegir dirigir la directiva a aplicaciones en dispositivos de cualquier estado de administración.
Dado que la administración de aplicaciones móviles no requiere administración de dispositivos, puedes proteger los datos de la empresa en dispositivos administrados y no administrados. La administración se centra en la identidad del usuario, que elimina el requisito de administración de dispositivos. Las empresas pueden usar directivas de protección de aplicaciones con o sin MDM al mismo tiempo. Por ejemplo, considere un empleado que usa un teléfono emitido por la compañía y su propia tableta personal. El teléfono de la empresa está inscrito en MDM y protegido por directivas de protección de aplicaciones mientras que el dispositivo personal está protegido solo por directivas de protección de aplicaciones.

    b. Seleccionar aplicaciones<br>
    Una aplicación administrada es una aplicación que tiene directivas de protección de aplicaciones aplicadas y que Intune puede administrar. Cualquier aplicación que se haya integrado con [el SDK](/mem/intune/developer/app-sdk) de Intune o que se haya ajustado mediante el App Wrapping Tool [Intune](/mem/intune/developer/apps-prepare-mobile-application-management) se puede administrar mediante directivas de protección de aplicaciones de Intune. Consulta la lista oficial de [aplicaciones Microsoft Intune protegidas](/mem/intune/apps/apps-supported-intune-apps) creadas con estas herramientas y que están disponibles para uso público.

    *Ejemplo: Outlook como una aplicación administrada*

    ![Imagen Outlook como aplicación administrada](images/managed-app.png)

 3. Establezca los requisitos de seguridad de inicio de sesión para la directiva de protección. <br>
Selecciona **Establecer > nivel máximo** de amenaza de dispositivo permitido en Condiciones del **dispositivo** y escribe un valor. A **continuación, seleccione Acción: "Bloquear acceso".** Microsoft Defender para Endpoint en Android comparte este nivel de amenaza de dispositivo.

    ![Imagen del inicio condicional](images/conditional-launch.png)

4. Asignar grupos de usuarios a los que se debe aplicar la directiva.<br>
  Seleccione **Grupos incluidos**. A continuación, agregue los grupos relevantes. 


Para obtener más información sobre mam o directiva de protección de aplicaciones, consulta configuración de la directiva de protección [de aplicaciones de iOS](/mem/intune/apps/app-protection-policy-settings-ios).

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Implementar Microsoft Defender para endpoint para MAM o en dispositivos no inscritos

Microsoft Defender para endpoint en iOS habilita el escenario de directiva de protección de aplicaciones y está disponible en la Tienda de aplicaciones de Apple.

Cuando las directivas de protección de aplicaciones están configuradas para que las aplicaciones incluyan señales de riesgo de dispositivos de Microsoft Defender para Endpoint, los usuarios se redirigirán para instalar Microsoft Defender para Endpoint al usar dichas aplicaciones. Como alternativa, los usuarios también pueden instalar la versión más reciente de la aplicación directamente desde la Tienda de aplicaciones de Apple.
