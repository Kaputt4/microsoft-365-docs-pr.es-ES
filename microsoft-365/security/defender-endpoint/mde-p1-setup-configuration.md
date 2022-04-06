---
title: Configuración y configuración de Microsoft Defender para punto de conexión Plan 1
description: Obtenga información sobre cómo configurar y configurar El plan 1 de Defender para punto de conexión. Revise los requisitos, planee el lanzamiento y configure el entorno.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/14/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 774139aa6ccbf0562d5f6a9bf14eb89550e865a8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665962"
---
# <a name="set-up-and-configure-microsoft-defender-for-endpoint-plan-1"></a>Configuración y configuración de Microsoft Defender para punto de conexión Plan 1

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

En este artículo se describe cómo configurar y configurar El plan 1 de Defender para punto de conexión. Tanto si tiene ayuda como si lo está haciendo usted mismo, puede usar este artículo como guía en toda la implementación.  

## <a name="the-setup-and-configuration-process"></a>Proceso de instalación y configuración

:::image type="content" source="images/mde-p1-deploymentflow.png" alt-text="Flujo de instalación e implementación de Microsoft Defender para punto de conexión Plan 1" lightbox="images/mde-p1-deploymentflow.png":::

El proceso de configuración y configuración general de Defender para el plan 1 de punto de conexión es el siguiente: <br/><br/>


| Número  | Paso  | Descripción  |
|:---------:|:---------|:---------|
| 1 | [Revisar los requisitos](#review-the-requirements)  | Enumera los requisitos de licencias, explorador, sistema operativo y centro de datos   |
| 2 | [Planear la implementación](#plan-your-deployment) | Enumera varios métodos de implementación que se deben tener en cuenta e incluye vínculos a más recursos para ayudarle a decidir qué método usar.  |
| 3 | [Configuración del entorno de inquilino](#set-up-your-tenant-environment) | Enumera las tareas para configurar el entorno de inquilino |
| 4 | [Asignación de roles y permisos](#assign-roles-and-permissions) | Enumera los roles y permisos que se deben tener en cuenta para el equipo de seguridad. <br/><br/>**SUGERENCIA**: En cuanto se asignan roles y permisos, el equipo de seguridad puede empezar a usar el portal de Microsoft 365 Defender. Para más información, consulte [Introducción](mde-plan1-getting-started.md). |
| 5 | [Incorporación a Defender para punto de conexión](#onboard-to-defender-for-endpoint) | Enumera varios métodos por sistema operativo para incorporarse al plan 1 de Defender para punto de conexión e incluye vínculos a información más detallada para cada método.  |
| 6  | [Configurar protección de última generación](#configure-next-generation-protection) | Describe cómo configurar los valores de protección de próxima generación en Microsoft Endpoint Manager  |
| 7  | [Configuración de las funcionalidades de reducción de la superficie expuesta a ataques](#configure-your-attack-surface-reduction-capabilities)        | Enumera los tipos de capacidades de reducción de superficie expuesta a ataques que puede configurar e incluye procedimientos con vínculos a más recursos.  |
 
## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos del plan 1 de Defender para punto de conexión:<br/><br/>

| Requisito | Descripción |
|:---|:---|
| Requisitos de licencias | Plan 1 de Defender para punto de conexión |
| Requisitos de los exploradores | Microsoft Edge <br/> Versión 11 de Internet Explorer <br/> Google Chrome |
| Sistemas operativos | Windows 10, versión 1709 o posterior <br/>macOS: 11.5 (Big Sur), 10.15.7 (Catalina) o 10.14.6 (Mojave) <br/>iOS <br/>Sistema operativo Android  |
| Datacenter | Una de las siguientes ubicaciones del centro de datos: <br/>- Unión Europea <br/>- Reino Unido <br/>- Estados Unidos |


## <a name="plan-your-deployment"></a>Planear la implementación

Al planear la implementación, puede elegir entre varias arquitecturas y métodos de implementación diferentes. Cada organización es única, por lo que tiene varias opciones que tener en cuenta, como se muestra en la tabla siguiente: <br/><br/>

| Método | Descripción |
|:---|:---|
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (incluido en Microsoft Endpoint Manager) | Uso de Intune para administrar puntos de conexión en un entorno nativo en la nube |
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Configuration Manager](/mem/configmgr/core/understand/introduction) (incluidos en Microsoft Endpoint Manager) | Uso de Intune y Configuration Manager para administrar puntos de conexión y cargas de trabajo que abarcan un entorno local y en la nube |
| [Configuration Manager](/mem/configmgr/core/understand/introduction) | Uso de Configuration Manager para proteger los puntos de conexión locales con la eficacia basada en la nube de Defender para punto de conexión |
| Script local descargado del portal de Microsoft 365 Defender | Uso de scripts locales en puntos de conexión para ejecutar un piloto o incorporar solo algunos dispositivos |

Para más información sobre las opciones de implementación, consulte [Planeamiento de la implementación de Defender para punto de conexión](deployment-strategy.md). Y descargue el siguiente póster: 

[:::image type="content" source="../../media/defender-endpoint/mde-deployment-strategy.png" alt-text="Miniatura del póster de estrategia de implementación":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)

**[Obtener el póster de implementación](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)**

> [!TIP]
> Para obtener información más detallada sobre cómo planear la implementación, consulte [Planeamiento de la implementación de Microsoft Defender para punto de conexión](deployment-strategy.md).

## <a name="set-up-your-tenant-environment"></a>Configuración del entorno de inquilino

La configuración del entorno de inquilino incluye tareas como:

- Comprobación de las licencias
- Configuración del inquilino
- Configuración del proxy (solo si es necesario)
- Asegurarse de que los sensores funcionan correctamente e informar de los datos a Defender para punto de conexión 

Estas tareas se incluyen en la fase de configuración de Defender para punto de conexión. Consulte [Configuración de Defender para punto de conexión](production-deployment.md).

## <a name="assign-roles-and-permissions"></a>Asignación de roles y permisos

Para acceder al portal de Microsoft 365 Defender, configure la configuración de Defender para punto de conexión o realice tareas, como realizar acciones de respuesta en las amenazas detectadas, se deben asignar los permisos adecuados. Defender para punto de conexión usa [roles integrados dentro de Azure Active Directory](/azure/active-directory/roles/permissions-reference). 

Microsoft recomienda asignar a los usuarios solo el nivel de permiso que necesitan para realizar sus tareas. Puede asignar permisos mediante la administración básica de permisos o mediante el [control de acceso basado en rol](rbac.md) (RBAC). 

- Con la administración básica de permisos, los administradores globales y los administradores de seguridad tienen acceso completo, mientras que los lectores de seguridad tienen acceso de solo lectura.
- Con RBAC, puede establecer permisos más granulares a través de más roles. Por ejemplo, puede tener lectores de seguridad, operadores de seguridad, administradores de seguridad, administradores de puntos de conexión, etc.


En la tabla siguiente se describen los roles clave que se deben tener en cuenta para Defender para punto de conexión en su organización: <br/><br/>

| Función | Descripción |
|:---|:---|
| Administradores globales (también conocidos como administradores globales) <br/><br/> *Como procedimiento recomendado, limite el número de administradores globales.* | Los administradores globales pueden realizar todo tipo de tareas. La persona que registró su empresa para Microsoft 365 o para Microsoft Defender para punto de conexión Plan 1 es un administrador global de forma predeterminada. <br/><br/> Los administradores globales pueden acceder o cambiar la configuración en todos los portales de Microsoft 365, como: <br/>- El Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) <br/>- Microsoft Endpoint Manager centro de administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))  |
| Administradores de seguridad (también conocidos como administradores de seguridad) | Los administradores de seguridad pueden realizar tareas de operador de seguridad, además de las siguientes tareas: <br/>- Supervisión de directivas relacionadas con la seguridad <br/>- Administración de amenazas y alertas de seguridad <br/>- Visualización de informes |
| Operador de seguridad | Los operadores de seguridad pueden realizar tareas de lector de seguridad, además de las siguientes tareas: <br/>- Visualización de información sobre amenazas detectadas <br/>- Investigar y responder a las amenazas detectadas  |
| Lector de seguridad | Los lectores de seguridad pueden realizar las siguientes tareas: <br/>- Visualización de directivas relacionadas con la seguridad en los servicios de Microsoft 365 <br/>- Visualización de amenazas y alertas de seguridad <br/>- Visualización de informes  |


> [!TIP]
> Para obtener más información sobre los roles de Azure Active Directory, consulte [Asignación de roles de administrador y no administrador a usuarios con Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Y, más información sobre los roles de Defender para punto de conexión, consulte [Control de acceso basado en](prepare-deployment.md#role-based-access-control) rol.

## <a name="onboard-to-defender-for-endpoint"></a>Incorporación a Defender para punto de conexión

Cuando esté listo para incorporar los puntos de conexión de su organización, puede elegir entre varios métodos, como se muestra en la tabla siguiente: <br/><br/>

|Sistema operativo de punto de conexión | Métodos de incorporación|
|---|---|
| Windows 10 | [Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Administrador de dispositivos](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts de VDI](configure-endpoints-vdi.md)  |
| macOS | [Scripts locales](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móvil](mac-install-with-other-mdm.md) |
| iOS |[Basado en aplicaciones](ios-install.md) |
| Android | [Microsoft Endpoint Manager](android-intune.md) |

A continuación, continúe con la configuración de la protección de última generación y las capacidades de reducción de la superficie expuesta a ataques.

## <a name="configure-next-generation-protection"></a>Configurar protección de última generación

Se recomienda usar [Microsoft Endpoint Manager](/mem) para administrar los dispositivos y la configuración de seguridad de la organización, como se muestra en la siguiente imagen:
 
:::image type="content" source="../../media/mde-p1/endpoint-policies.png" alt-text="Directivas de seguridad de puntos de conexión en el portal de Micorosft Endpoint Manager" lightbox="../../media/mde-p1/endpoint-policies.png":::

Para configurar la protección de próxima generación en Microsoft Endpoint Manager, siga estos pasos:

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Seleccione **Seguridad** >  del **punto de conexiónAntivirus** y, a continuación, seleccione una directiva existente. (Si no tiene una directiva existente, cree una nueva).

3. Establezca o cambie la configuración del antivirus. ¿Necesita ayuda? Consulte los siguientes recursos: <br/>

   - [Configuración para la directiva de Windows 10 Antivirus de Microsoft Defender en Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)
   - [Configuración de Defender para punto de conexión en características de iOS](ios-configure-features.md)

4. Cuando haya terminado de especificar la configuración, elija **Revisar y guardar**.

## <a name="configure-your-attack-surface-reduction-capabilities"></a>Configuración de las funcionalidades de reducción de la superficie expuesta a ataques

La reducción de la superficie expuesta a ataques consiste en reducir los lugares y las formas en que su organización está abierta a los ataques. El plan 1 de Defender para punto de conexión incluye varias características y funcionalidades que le ayudarán a reducir las superficies expuestas a ataques en los puntos de conexión. Estas características y funcionalidades se enumeran en la tabla siguiente: <br/><br/>

| Característica o funcionalidad | Descripción |
|:---|:---|
| [Reglas de la reducción de la superficie expuesta a ataques](#attack-surface-reduction-rules) | Configure reglas de reducción de la superficie expuesta a ataques para restringir los comportamientos de riesgo basados en software y ayudar a mantener la seguridad de su organización. Las reglas de reducción de superficie expuesta a ataques tienen como destino determinados comportamientos de software, como<br/>- Iniciar archivos ejecutables y scripts que intentan descargar o ejecutar archivos <br/>- Ejecución de scripts ofuscados o sospechosos <br/>- Realizar comportamientos que las aplicaciones no suelen iniciar durante el trabajo diario normal <br/><br/>Estos comportamientos de software a veces se ven en aplicaciones legítimas. Sin embargo, estos comportamientos a menudo se consideran de riesgo porque suelen ser objeto de abuso por parte de los atacantes a través de malware.  |
| [Mitigación de ransomware](#ransomware-mitigation) | Configure la mitigación de ransomware mediante la configuración del acceso controlado a carpetas, lo que ayuda a proteger los datos valiosos de su organización frente a aplicaciones y amenazas malintencionadas, como ransomware. | 
| [Control de dispositivos](#device-control) | Configure las opciones de control de dispositivos de su organización para permitir o bloquear dispositivos extraíbles (como unidades USB). | 
| [Protección de red](#network-protection) | Configure la protección de red para evitar que las personas de su organización usen aplicaciones que accedan a dominios peligrosos o contenido malintencionado en Internet. |
| [Protección web](#web-protection) | Configure la protección contra amenazas web para proteger los dispositivos de su organización frente a sitios de phishing, sitios de vulnerabilidades de seguridad y otros sitios que no son de confianza o de baja reputación. Configure el filtrado de contenido web para realizar un seguimiento y regular el acceso a los sitios web en función de sus categorías de contenido (como ocio, ancho de banda alto, contenido para adultos o responsabilidad legal). |
| [Firewall de red](#network-firewall) | Configure el firewall de red con reglas que determinen qué tráfico de red puede entrar o salir de los dispositivos de la organización. |
| [Control de la aplicación](#application-control)  | Configure las reglas de control de aplicaciones si desea permitir que solo se ejecuten aplicaciones y procesos de confianza en los dispositivos Windows.    |

### <a name="attack-surface-reduction-rules"></a>Reglas de reducción de la superficie expuesta a ataques

Las reglas de reducción de superficie expuesta a ataques están disponibles en dispositivos que ejecutan Windows. Se recomienda usar Microsoft Endpoint Manager, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Reglas de reducción de superficie expuesta a ataques en el portal de Microsoft Endpoint Manager" lightbox="../../media/mde-p1/mem-asrpolicies.png":::

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Elija **Seguridad de** >  los puntos de **conexiónRed de superficie de** >  ataque **+ Crear directiva**.

3. En **Plataforma**, seleccione **Windows 10 y versiones posteriores**.

4. En **Perfil**, seleccione **Reglas de reducción de superficie expuesta a ataques** y, a continuación, elija **Crear**.

5. En la pestaña **Aspectos básicos** , especifique un nombre y una descripción para la directiva y, a continuación, elija **Siguiente**.

6. En la pestaña **Configuración** , expanda **Reglas de reducción de superficie expuesta a ataques**.

7. Especifique la configuración de cada regla y, a continuación, elija **Siguiente**. (Para obtener más información sobre lo que hace cada regla, consulte [Reglas de reducción de superficie expuesta a ataques](attack-surface-reduction.md)). 

8. En la pestaña **Etiquetas** de ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar etiquetas de ámbito** y, a continuación, seleccione las etiquetas que desea usar. A continuación, elija **Siguiente**. 
   
   Para más información sobre las etiquetas de ámbito, consulte [Uso del control de acceso basado en rol (RBAC) y las etiquetas de ámbito para TI distribuida](/mem/intune/fundamentals/scope-tags).

9. En la pestaña **Asignaciones** , especifique los usuarios y grupos a los que se debe aplicar la directiva y, a continuación, elija **Siguiente**. (Para obtener más información sobre las asignaciones, consulte [Asignación de perfiles de usuario y dispositivo en Microsoft Intune](/mem/intune/configuration/device-profile-assign)).

10. En la pestaña **Revisar y crear** , revise la configuración y, a continuación, elija **Crear**.

> [!TIP]
> Para obtener más información sobre las reglas de reducción de superficie expuesta a ataques, consulte los siguientes recursos:
> - [Usar reglas de reducción de la superficie expuesta a ataques para evitar la infección de malware](attack-surface-reduction.md)
> - [Ver la lista de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md)
> - [Implementación de reglas de reducción de superficie expuesta a ataques Paso 3: Implementar reglas ASR](attack-surface-reduction-rules-deployment-implement.md)

### <a name="ransomware-mitigation"></a>Mitigación de ransomware

Obtiene la mitigación de ransomware a través del [acceso controlado a carpetas](controlled-folders.md#what-is-controlled-folder-access), lo que solo permite que las aplicaciones de confianza accedan a carpetas protegidas en los puntos de conexión. 

Se recomienda usar Microsoft Endpoint Manager para configurar el acceso controlado a carpetas.

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Directivas de ASR en el portal de Microsoft Endpoint Manager" lightbox="../../media/mde-p1/mem-asrpolicies.png":::

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión. 

2. Seleccione **Seguridad del punto de conexión** y, a continuación, seleccione **Reducción de superficie expuesta a ataques**.

3. Elija **+ Crear directiva**. 

4. En **Plataforma**, seleccione **Windows 10 y versiones posteriores** y, en **Perfil**, seleccione **Reglas de reducción de superficie expuesta a ataques**. Después, haga clic en **Crear**. 

5. En la pestaña **Aspectos básicos** , asigne un nombre a la directiva y agregue una descripción. Seleccione **Siguiente**. 

6. En la pestaña **Configuración** , en la sección **Reglas de reducción de superficie expuesta a ataques** , desplácese hacia abajo hasta la parte inferior. En la lista desplegable **Habilitar protección de carpetas** , seleccione **Habilitar**. Opcionalmente, puede especificar estas otras opciones:

   - Junto a **Lista de carpetas adicionales que deben protegerse**, seleccione el menú desplegable y agregue carpetas que deben protegerse.
   - Junto a **Lista de aplicaciones que tienen acceso a carpetas protegidas**, seleccione el menú desplegable y, a continuación, agregue aplicaciones que deben tener acceso a carpetas protegidas.
   - Junto a **Excluir archivos y rutas de acceso de las reglas de reducción de superficie expuesta a ataques**, seleccione el menú desplegable y agregue los archivos y rutas de acceso que deben excluirse de las reglas de reducción de superficie expuesta a ataques.

   A continuación, elija **Siguiente**.

7. En la pestaña **Etiquetas** de ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar etiquetas de ámbito** y, a continuación, seleccione las etiquetas que desea usar. A continuación, elija **Siguiente**. 
   
   Para más información sobre las etiquetas de ámbito, consulte [Uso del control de acceso basado en rol (RBAC) y las etiquetas de ámbito para TI distribuida](/mem/intune/fundamentals/scope-tags).

8. En la pestaña **Asignaciones** , seleccione **Agregar todos los usuarios** y **+ Agregar todos los dispositivos** y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

9. En la pestaña **Revisar y crear** , revise la configuración de la directiva y, a continuación, elija **Crear**. La directiva se aplicará a cualquier punto de conexión que se haya incorporado a Defender para punto de conexión en breve.

### <a name="device-control"></a>Control de dispositivo

Puede configurar Defender para punto de conexión para bloquear o permitir dispositivos y archivos extraíbles en dispositivos extraíbles. Se recomienda usar Microsoft Endpoint Manager para configurar los valores de control del dispositivo.

:::image type="content" source="../../media/mde-p1/mem-admintemplates.png" alt-text="plantillas administrativas de Microsoft Endpoint Manager" lightbox="../../media/mde-p1/mem-admintemplates.png":::

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión. 

2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.

3. En **Plataforma**, seleccione **Windows 10 y versiones posteriores** y, en **Tipo de perfil**, seleccione **Plantillas**. 

   En **Nombre de plantilla**, seleccione **Plantillas administrativas** y, a continuación, elija **Crear**. 

4. En la pestaña **Aspectos básicos** , asigne un nombre a la directiva y agregue una descripción. Seleccione **Siguiente**. 

5. En la pestaña **Configuración**, seleccione **Todos los Configuración**. A continuación, en el cuadro de búsqueda, escriba `Removable` para ver todas las configuraciones que pertenecen a los dispositivos extraíbles.

6. Seleccione un elemento de la lista, como **Todas las clases de Storage extraíbles: Denegar todo el acceso**, para abrir su panel flotante. El control flotante de cada configuración explica lo que ocurre cuando está habilitado, deshabilitado o no configurado. Seleccione una configuración y, a continuación, elija **Aceptar**. 

7. Repita el paso 6 para cada configuración que quiera configurar. A continuación, elija **Siguiente**.

8. En la pestaña **Etiquetas** de ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar etiquetas de ámbito** y, a continuación, seleccione las etiquetas que desea usar. A continuación, elija **Siguiente**. 
   
   Para más información sobre las etiquetas de ámbito, consulte [Uso del control de acceso basado en rol (RBAC) y las etiquetas de ámbito para TI distribuida](/mem/intune/fundamentals/scope-tags).

9. En la pestaña **Asignaciones** , seleccione **Agregar todos los usuarios** y **+ Agregar todos los dispositivos** y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

10. En la pestaña **Revisar y crear** , revise la configuración de la directiva y, a continuación, elija **Crear**. La directiva se aplicará a cualquier punto de conexión que se haya incorporado a Defender para punto de conexión en breve.

> [!TIP]
> Para obtener más información, consulte [Control de dispositivos USB y otros medios extraíbles mediante Microsoft Defender para punto de conexión](control-usb-devices-using-intune.md).

### <a name="network-protection"></a>Protección de red

Con la protección de red, puede ayudar a proteger su organización contra dominios peligrosos que podrían hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet. Se recomienda usar Microsoft Endpoint Manager para activar la protección de red.

:::image type="content" source="../../media/mde-p1/mem-endpointprotectionprofile.png" alt-text="Perfil de Endpoint Protection en el portal de Microsoft Endpoint Manager" lightbox="../../media/mde-p1/mem-endpointprotectionprofile.png":::

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión. 

2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.

3. En **Plataforma**, seleccione **Windows 10 y versiones posteriores** y, en **Tipo de perfil**, seleccione **Plantillas**. 

   En **Nombre de plantilla**, seleccione **Endpoint Protection** y, a continuación, elija **Crear**. 

4. En la pestaña **Aspectos básicos** , asigne un nombre a la directiva y agregue una descripción. Seleccione **Siguiente**. 

5. En la pestaña **Configuración**, expanda **Protección contra vulnerabilidades de seguridad de Microsoft Defender** y, a continuación, expanda **Filtrado de red**.

   Establezca **Protección de red** en **Habilitar**. (También puede elegir **Auditar** para ver cómo funcionará la protección de red en el entorno al principio).

   A continuación, elija **Siguiente**.

6. En la pestaña **Asignaciones** , seleccione **Agregar todos los usuarios** y **+ Agregar todos los dispositivos** y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

7. En la pestaña **Reglas de aplicabilidad** , configure una regla. El perfil que va a configurar solo se aplicará a los dispositivos que cumplan los criterios combinados que especifique. 

   Por ejemplo, puede optar por asignar la directiva a los puntos de conexión que ejecutan solo una edición del sistema operativo determinada.

   A continuación, elija **Siguiente**. 

8. En la pestaña **Revisar y crear** , revise la configuración de la directiva y, a continuación, elija **Crear**. La directiva se aplicará a cualquier punto de conexión que se haya incorporado a Defender para punto de conexión en breve.

> [!TIP]
> Puede usar otros métodos, como Windows PowerShell o directiva de grupo, para habilitar la protección de red. Para más información, consulte [Activación de la protección de red](enable-network-protection.md).

### <a name="web-protection"></a>Protección web

Con la protección web, puede proteger los dispositivos de su organización frente a amenazas web y contenido no deseado. La protección web incluye [protección contra amenazas web](#configure-web-threat-protection) y [filtrado de contenido web](#configure-web-content-filtering). Configure ambos conjuntos de funcionalidades. Se recomienda usar Microsoft Endpoint Manager para configurar los valores de protección web.

#### <a name="configure-web-threat-protection"></a>Configuración de la protección contra amenazas web

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.
 
2. Elija Seguridad  > **de los puntos de conexiónRed** de **superficie** y, a continuación, elija **+ Crear directiva**.

3. Seleccione una plataforma, como **Windows 10 y versiones posteriores**, seleccione el perfil **de protección web** y, a continuación, elija **Crear**. 

4. En la pestaña **Aspectos básicos** , especifique un nombre y una descripción y, a continuación, elija **Siguiente**.

5. En la pestaña **Configuración** , expanda **Protección web**, especifique la configuración de la tabla siguiente y, a continuación, elija **Siguiente**. <br/><br/>

   | Valor | Recomendación |
   |:---|:---|
   | **Habilitación de la protección de red** | Establézcalo **en Habilitado**. Impide que los usuarios visiten sitios o dominios malintencionados. <br/><br/>Como alternativa, puede establecer la protección de red en **modo auditoría** para ver cómo funcionará en su entorno. En el modo de auditoría, la protección de red no impide que los usuarios visiten sitios o dominios, pero realiza un seguimiento de las detecciones como eventos. |
   | **Requerir SmartScreen para Microsoft Edge (versión anterior)** | Establézcalo en **Sí**. Ayuda a proteger a los usuarios de posibles estafas de suplantación de identidad (phishing) y software malintencionado. |
   | **Bloquear el acceso a sitios malintencionados** | Establézcalo en **Sí**. Impide que los usuarios omitan advertencias sobre sitios potencialmente malintencionados. |
   | **Bloquear la descarga de archivos no comprobados** | Establézcalo en **Sí**. Impide que los usuarios omitan las advertencias y descarguen archivos no comprobados. |

6. En la pestaña **Etiquetas** de ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar etiquetas de ámbito** y, a continuación, seleccione las etiquetas que desea usar. A continuación, elija **Siguiente**. 
   
   Para más información sobre las etiquetas de ámbito, consulte [Uso del control de acceso basado en rol (RBAC) y las etiquetas de ámbito para TI distribuida](/mem/intune/fundamentals/scope-tags).

7. En la pestaña **Asignaciones** , especifique los usuarios y dispositivos para recibir la directiva de protección web y, a continuación, elija **Siguiente**.

8. En la pestaña **Revisar y crear** , revise la configuración de la directiva y, a continuación, elija **Crear**.

> [!TIP]
> Para obtener más información sobre la protección contra amenazas web, consulte [Protección de su organización frente a amenazas web](web-threat-protection.md).

#### <a name="configure-web-content-filtering"></a>Configuración del filtrado de contenido web

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) e inicie sesión.

2. Elija **Configuración** >  **Endpoints**.

3. En **Reglas**, elija **Filtrado de contenido web** y, a continuación, elija **+ Agregar directiva**.

4. En el control flotante **Agregar directiva** , en la pestaña **General** , especifique un nombre para la directiva y, a continuación, elija **Siguiente**.

5. En Categorías **bloqueadas**, seleccione una o varias categorías que quiera bloquear y, a continuación, elija **Siguiente**.

6. En la pestaña **Ámbito** , seleccione los grupos de dispositivos que desea recibir esta directiva y, a continuación, elija **Siguiente**.

7. En la pestaña **Resumen** , revise la configuración de la directiva y, a continuación, elija **Guardar**.

> [!TIP]
> Para más información sobre cómo configurar el filtrado de contenido web, consulte [Filtrado de contenido web](web-content-filtering.md).

### <a name="network-firewall"></a>Firewall de red

El firewall de red ayuda a reducir el riesgo de amenazas de seguridad de red. El equipo de seguridad puede establecer reglas que determinen qué tráfico puede fluir hacia o desde los dispositivos de la organización. Se recomienda usar Microsoft Endpoint Manager para configurar el firewall de red. 

:::image type="content" source="../../media/mde-p1/mem-firewallpolicy.png" alt-text="Directiva de firewall en el portal de Microsoft Endpoint Manager" lightbox="../../media/mde-p1/mem-firewallpolicy.png":::

Para configurar los valores básicos del firewall, siga estos pasos:

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Elija Seguridad  > **del punto de** **conexiónFirewall** y, a continuación, elija **+ Crear directiva**.

3. Seleccione una plataforma, como **Windows 10 y versiones posteriores**, seleccione el perfil **firewall de Microsoft Defender** y, a continuación, elija **Crear**. 

4. En la pestaña **Aspectos básicos** , especifique un nombre y una descripción y, a continuación, elija **Siguiente**.

5. Expanda **Firewall de Microsoft Defender** y desplácese hacia abajo hasta la parte inferior de la lista.

6. Establezca cada una de las opciones siguientes en **Sí**:

   - **Activar firewall de Microsoft Defender para redes de dominio** 
   - **Activar firewall de Microsoft Defender para redes privadas**
   - **Activar firewall de Microsoft Defender para redes públicas**
   
   Revise la lista de configuraciones en cada una de las redes de dominio, redes privadas y redes públicas. Puede dejarlos establecidos en **No configurados** o cambiarlos para que se adapten a las necesidades de su organización.

   A continuación, elija **Siguiente**.

7. En la pestaña **Etiquetas** de ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar etiquetas de ámbito** y, a continuación, seleccione las etiquetas que desea usar. A continuación, elija **Siguiente**. 
   
   Para más información sobre las etiquetas de ámbito, consulte [Uso del control de acceso basado en rol (RBAC) y las etiquetas de ámbito para TI distribuida](/mem/intune/fundamentals/scope-tags).

8. En la pestaña **Asignaciones** , seleccione **Agregar todos los usuarios** y **+ Agregar todos los dispositivos** y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

9. En la pestaña **Revisar y crear** , revise la configuración de la directiva y, a continuación, elija **Crear**.

> [!TIP]
> La configuración del firewall se detalla y puede parecer compleja. Consulte [Procedimientos recomendados para configurar Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/best-practices-configuring).

### <a name="application-control"></a>Control de la aplicación

Windows Defender Control de aplicaciones (WDAC) ayuda a proteger los puntos de conexión de Windows al permitir que solo se ejecuten aplicaciones y procesos de confianza. La mayoría de las organizaciones usaban una implementación por fases de WDAC. Es decir, la mayoría de las organizaciones no implementa WDAC en todos los puntos de conexión de Windows al principio. De hecho, dependiendo de si los puntos de conexión de Windows de su organización están totalmente administrados, administrados ligeramente o "Traiga su propio dispositivo", puede implementar WDAC en todos o algunos puntos de conexión.

Para ayudar a planear la implementación de WDAC, consulte los siguientes recursos:

- [Control de aplicaciones para Windows](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender decisiones de diseño de directivas de Application Control](/windows/security/threat-protection/windows-defender-application-control/understand-windows-defender-application-control-policy-design-decisions)

- [Windows Defender implementación de Application Control en diferentes escenarios: tipos de dispositivos](/windows/security/threat-protection/windows-defender-application-control/types-of-devices)

## <a name="next-steps"></a>Siguientes pasos

Ahora que ha pasado por el proceso de configuración y configuración, el siguiente paso es empezar a usar Defender para punto de conexión. 

- [Comenzar con el plan 1 de Defender para punto de conexión](mde-plan1-getting-started.md)
