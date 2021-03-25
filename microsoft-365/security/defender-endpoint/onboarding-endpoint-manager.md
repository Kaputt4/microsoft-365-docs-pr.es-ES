---
title: Incorporación con Microsoft Endpoint Manager
description: Obtenga información sobre cómo incorporarse a Microsoft Defender para endpoint con Microsoft Endpoint Manager
keywords: incorporación, configuración, implementación, implementación, administrador de puntos de conexión, mdatp, protección contra amenazas avanzada, creación de colecciones, respuesta de detección de puntos de conexión, protección de próxima generación, reducción de superficie de ataque, administrador de puntos de conexión de Microsoft
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9edcceca2f6cc7c2377eb388d7394a23dfbae99d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186262"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Incorporación con Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este artículo forma parte de la guía de implementación y actúa como un método de incorporación de ejemplo. 

En el [tema Planeación,](deployment-strategy.md) se proporcionaron varios métodos para incorporar dispositivos al servicio. En este tema se trata la arquitectura nativa de la nube. 

![Imagen de arquitectura nativa de la nube ](images/cloud-native-architecture.png)
 *Diagrama de arquitecturas de entorno*

Aunque Defender para endpoint admite la incorporación de varios puntos de conexión y herramientas, este artículo no los cubre. Para obtener información sobre la incorporación general con otras herramientas y métodos de implementación compatibles, vea [Onboarding overview](onboarding.md).


[Microsoft Endpoint Manager es](https://docs.microsoft.com/mem/endpoint-manager-overview) una plataforma de soluciones que unifica varios servicios. Incluye [Microsoft Intune para](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) la administración de dispositivos basados en la nube.


En este tema se guía a los usuarios en:
- Paso 1: Incorporación de dispositivos al servicio mediante la creación de un grupo en Microsoft Endpoint Manager (MEM) para asignar configuraciones en
- Paso 2: Configuración de las capacidades de Defender para endpoints con Microsoft Endpoint Manager

Esta guía de incorporación le ayudará a seguir los siguientes pasos básicos que debe seguir al usar Microsoft Endpoint Manager:

-   [Identificación de dispositivos o usuarios de destino](#identify-target-devices-or-users)

    -   Creación de un grupo de Azure Active Directory (usuario o dispositivo)

-   [Creación de un perfil de configuración](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   En Microsoft Endpoint Manager, le guiaremos en la creación de una directiva independiente para cada funcionalidad.





## <a name="resources"></a>Recursos


Estos son los vínculos que necesitará para el resto del proceso:

-   [Portal MEM](https://aka.ms/memac)

-   [Centro de seguridad](https://securitycenter.windows.com/)

-   [Líneas base de seguridad de Intune](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Para obtener más información acerca de Microsoft Endpoint Manager, consulte estos recursos:
- [Página de Microsoft Endpoint Manager](https://docs.microsoft.com/mem/)
- [Entrada de blog sobre la convergencia de Intune y ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Vídeo de introducción en MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Paso 1: Incorporar dispositivos mediante la creación de un grupo en MEM para asignar configuraciones en
### <a name="identify-target-devices-or-users"></a>Identificar dispositivos o usuarios de destino
En esta sección, crearemos un grupo de prueba para asignar las configuraciones.

>[!NOTE]
>Intune usa grupos de Azure Active Directory (Azure AD) para administrar dispositivos y usuarios. Como administrador de Intune, puede configurar grupos que se adapten a sus necesidades organizativas.<br>
Para obtener más información, consulta [Agregar grupos para organizar usuarios y dispositivos.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-a-group"></a>Crear un grupo

1.  Abra el portal de MEM.

2.  Abra **Grupos > Nuevo grupo**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager1](images/66f724598d9c3319cba27f79dd4617a4.png)

3.  Escriba los detalles y cree un nuevo grupo.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4.  Agrega el usuario o dispositivo de prueba.

5.  En el **panel > todos los grupos,** abra el nuevo grupo.

6.  Seleccione  **Miembros > Agregar miembros**.

7.  Busca el usuario o dispositivo de prueba y selecciónelo.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8.  El grupo de pruebas ahora tiene un miembro que probar.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Paso 2: Crear directivas de configuración para configurar las capacidades de Microsoft Defender para puntos de conexión
En la siguiente sección, creará una serie de directivas de configuración.

Primero es una directiva de configuración para seleccionar qué grupos de usuarios o dispositivos se incorporarán a Defender for Endpoint:

- [Detección y respuesta de puntos de conexión.](#endpoint-detection-and-response) 

A continuación, seguirá creando varios tipos diferentes de directivas de seguridad de extremo:

- [Protección de última generación](#next-generation-protection)
- [Reducción de la superficie expuesta a ataques](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Detección y respuesta de puntos de conexión.

1.  Abra el portal de MEM.

2.  Vaya a **Seguridad de > de detección y respuesta del extremo**. Haga clic en **Crear perfil**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager4](images/58dcd48811147feb4ddc17212b7fe840.png)

3.  En **Plataforma, selecciona Windows 10 y versiones posteriores, Perfil: detección de puntos de** conexión y respuesta > Crear .

4.  Escriba un nombre y una descripción y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5.  Seleccione la configuración según sea necesario y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > En este caso, esto se ha rellenado automáticamente como Defender para endpoint ya se ha integrado con Intune. Para obtener más información sobre la integración, vea [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).
    > 
    > La siguiente imagen es un ejemplo de lo que verá cuando Microsoft Defender para Endpoint no esté integrado con Intune:
    >
    > ![Imagen del portal de Microsoft Endpoint Manager7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  Agregue etiquetas de ámbito si es necesario y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7.  Para agregar un grupo de prueba, haga clic en **Seleccionar grupos para incluir** y elegir el grupo y, a continuación, seleccione  **Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8.  Revise y acepte y, a continuación,  **seleccione Crear**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9.  Puede ver la directiva completada.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Protección de última generación

1.  Abra el portal de MEM.

2.  Vaya a **Endpoint security > Antivirus > Create Policy**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3.  Seleccione **Plataforma - Windows 10 y versiones posteriores - Windows y Perfil : Antivirus** de Microsoft Defender > Crear .

4.  Escriba el nombre y la descripción y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5.  En la **página Configuración:** establezca las configuraciones que necesita para Antivirus de Microsoft Defender (protección en la nube, exclusiones, Real-Time protección y corrección).

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6.  Agregue etiquetas de ámbito si es necesario y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7.  Seleccione los grupos que desea incluir, asígnelos al grupo de prueba y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager16](images/48318a51adee06bff3908e8ad4944dc9.png)

8.  Revise y cree y, a continuación,  **seleccione Crear**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager17](images/dfdadab79112d61bd3693d957084b0ec.png)

9.  Verá la directiva de configuración que creó.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Reducción de superficie de ataque: reglas de reducción de superficie de ataque

1.  Abra el portal de MEM.

2.  Navegue hasta **Endpoint security > Reducción de superficie de ataque**.

3.  Seleccione  **Crear directiva**.

4.  Selecciona **Plataforma - Windows 10 y versiones posteriores: Perfil: reglas de** reducción de superficie > Crear .

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5.  Escriba un nombre y una descripción y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6.  En la **página Configuración:** Establezca las configuraciones que necesita para las reglas de reducción de superficie de ataque y, a continuación,  **seleccione Siguiente**.

    > [!NOTE]
    > Configuraremos todas las reglas de reducción de superficie de ataque en Auditar.
    > 
    > Para obtener más información, consulta [Reglas de reducción de superficie de ataque](attack-surface-reduction.md).

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager21](images/dd0c00efe615a64a4a368f54257777d0.png)

7.  Agregue etiquetas de ámbito según sea necesario y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Seleccione los grupos que desea incluir y asignar al grupo de prueba y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Revise los detalles y, a continuación,  **seleccione Crear**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Ver la directiva.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Reducción de superficie de ataque: protección web

1.  Abra el portal de MEM.

2.  Navegue hasta **Endpoint security > Reducción de superficie de ataque**.

3.  Seleccione  **Crear directiva**.

4.  Seleccione **Windows 10 y versiones posteriores: protección > Crear**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5.  Escriba un nombre y una descripción y, a continuación,  **seleccione Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6.  En la **página Configuración:** Establezca las configuraciones que necesita para Protección web y, a continuación,  **seleccione Siguiente**.

    > [!NOTE]
    > Estamos configurando Protección web para bloquear.
    > 
    > Para obtener más información, vea [Web Protection](web-protection-overview.md).

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7.  Agregue **etiquetas de ámbito según > Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Seleccione **Asignar a grupo de prueba > Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager30](images/45cefc8e4e474321b4d47b4626346597.png)

9.  Seleccione **Revisar y Crear > Crear**.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Ver la directiva.

    > [!div class="mx-imgBorder"]
    > ![Imagen del portal de Microsoft Endpoint Manager32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Validar opciones de configuración


### <a name="confirm-policies-have-been-applied"></a>Confirmar que se han aplicado directivas


Una vez asignada la directiva de configuración, llevará algún tiempo aplicarla.

Para obtener información sobre el tiempo, consulta [Información de configuración de Intune](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Para confirmar que la directiva de configuración se ha aplicado al dispositivo de prueba, siga el siguiente proceso para cada directiva de configuración.

1.  Abra el portal de MEM y vaya a la directiva correspondiente, como se muestra en los pasos anteriores. En el ejemplo siguiente se muestra la configuración de protección de próxima generación.

    > [!div class="mx-imgBorder"]
    > [![Imagen del portal de Microsoft Endpoint Manager33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2.  Seleccione la **directiva de configuración** para ver el estado de la directiva.

    > [!div class="mx-imgBorder"]
    > [![Imagen del portal de Microsoft Endpoint Manager34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3.  Selecciona  **Estado del dispositivo** para ver el estado.

    > [!div class="mx-imgBorder"]
    > [![Imagen del portal de Microsoft Endpoint Manager35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4.  Seleccione  **Estado de usuario** para ver el estado.

    > [!div class="mx-imgBorder"]
    > [![Imagen del portal de Microsoft Endpoint Manager36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5.  Seleccione  **Estado por configuración para** ver el estado.

    >[!TIP]
    >Esta vista es muy útil para identificar cualquier configuración que entre en conflicto con otra directiva.

    > [!div class="mx-imgBorder"]
    > [![Imagen del portal de Microsoft Endpoint Manager37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Detección y respuesta de puntos de conexión.


1.  Antes de aplicar la configuración, no se debe iniciar el servicio defender para Endpoint Protection.

    > [!div class="mx-imgBorder"]
    > [![Imagen del panel de servicios1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2.  Una vez aplicada la configuración, debe iniciarse el servicio defender para Endpoint Protection.

    > [!div class="mx-imgBorder"]
    > [![Imagen del panel de servicios2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3.  Una vez que los servicios se ejecutan en el dispositivo, el dispositivo aparece en el Centro de seguridad de Microsoft Defender.

    > [!div class="mx-imgBorder"]
    > [![Imagen del Centro de seguridad de Microsoft Defender ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Protección de última generación

1.  Antes de aplicar la directiva en un dispositivo de prueba, debes poder administrar manualmente la configuración como se muestra a continuación.

    > [!div class="mx-imgBorder"]
    > ![Imagen de la página de configuración1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2.  Después de aplicar la directiva, no debería poder administrar manualmente la configuración.

    > [!NOTE]
    > En la siguiente **imagen, se muestran como administrados Activar** la protección entregada en la nube y Activar la protección en tiempo real. 

    > [!div class="mx-imgBorder"]
    > ![Imagen de la página de configuración2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Reducción de superficie de ataque: reglas de reducción de superficie de ataque


1.  Antes de aplicar la directiva en un dispositivo de prueba, escriba una ventana de PowerShell y escriba `Get-MpPreference` .

2.  Esto debe responder con las siguientes líneas sin contenido:

    > AttackSurfaceReductionOnlyExclusions:
    > 
    > AttackSurfaceReductionRules_Actions:
    > 
    > AttackSurfaceReductionRules_Ids:

    ![Imagen de la línea de comandos1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  Después de aplicar la directiva en un dispositivo de prueba, abra un Windows de PowerShell y escriba `Get-MpPreference` .

4.  Esto debe responder con las siguientes líneas con contenido como se muestra a continuación:

    ![Imagen de la línea de comandos2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Reducción de superficie de ataque: protección web

1.  En el dispositivo de prueba, abra un Windows de PowerShell y escriba `(Get-MpPreference).EnableNetworkProtection` .

2.  Esto debe responder con un 0 como se muestra a continuación.

    ![Imagen de la línea de comandos3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  Después de aplicar la directiva, abra un Windows de PowerShell y escriba `(Get-MpPreference).EnableNetworkProtection` .

4.  Esto debe responder con un 1 como se muestra a continuación.

    ![Imagen de la línea de comandos4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
