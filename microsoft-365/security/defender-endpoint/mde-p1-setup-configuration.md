---
title: Configurar y configurar Microsoft Defender para el plan de extremo 1
description: Obtenga información sobre cómo configurar y configurar Defender for Endpoint Plan 1. Revise los requisitos, planee su implementación y configure el entorno.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 11/19/2021
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: 03f9a8268ac3d1652840a9d99d3493358cf71ee4
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2021
ms.locfileid: "61128021"
---
# <a name="set-up-and-configure-microsoft-defender-for-endpoint-plan-1"></a>Configurar y configurar Microsoft Defender para el plan de extremo 1

> [!TIP]
> Si tiene Microsoft 365 E3 O A3 pero no Microsoft 365 E5 o A5, visite [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) para registrarse en el programa de vista previa.

En este artículo se describe cómo configurar y configurar Defender for Endpoint Plan 1. Tanto si tiene asistencia como si lo está haciendo usted mismo, puede usar este artículo como guía durante toda la implementación.  

## <a name="the-setup-and-configuration-process"></a>Proceso de configuración y configuración

:::image type="content" source="images/mde-p1-deploymentflow.png" alt-text="Flujo de instalación e implementación de Microsoft Defender para endpoint plan 1":::

El proceso general de configuración y configuración de Defender for Endpoint Plan 1 es el siguiente: <br/><br/>


| Número  | Paso  | Descripción  |
|:---------:|:---------|:---------|
| 1 | [Revisar los requisitos](#review-the-requirements)  | Enumera los requisitos de licencias, explorador, sistema operativo y centro de datos   |
| 2 | [Planear la implementación](#plan-your-deployment) | Enumera varios métodos de implementación a tener en cuenta e incluye vínculos a más recursos para ayudarle a decidir qué método usar  |
| 3 | [Configurar el entorno de inquilino](#set-up-your-tenant-environment) | Enumera las tareas para configurar el entorno de inquilino |
| 4 | [Asignar roles y permisos](#assign-roles-and-permissions) | Enumera los roles y permisos que se deben tener en cuenta para el equipo de seguridad <br/><br/>**SUGERENCIA:** Tan pronto como se asignan roles y permisos, el equipo de seguridad puede empezar a usar el portal Microsoft 365 Defender seguridad. Para obtener más información, vea [Introducción.](mde-plan1-getting-started.md) |
| 5 | [Incorporación a Defender para endpoint](#onboard-to-defender-for-endpoint) | Enumera varios métodos por sistema operativo para incorporar a Defender for Endpoint Plan 1 e incluye vínculos a información más detallada para cada método  |
| 6  | [Configurar protección de última generación](#configure-next-generation-protection) | Describe cómo configurar las opciones de protección de próxima generación en Microsoft Endpoint Manager  |
| 7  | [Configurar las capacidades de reducción de superficie de ataque](#configure-your-attack-surface-reduction-capabilities)        | Enumera los tipos de capacidades de reducción de superficie de ataque que puedes configurar e incluye procedimientos con vínculos a más recursos  |
 
## <a name="review-the-requirements"></a>Revisar los requisitos

En la tabla siguiente se enumeran los requisitos básicos para Defender para el plan de extremo 1:<br/><br/>

| Requisito | Descripción |
|:---|:---|
| Requisitos de licencias | Defender for Endpoint Plan 1 <br/><br/>*Si tiene una Microsoft 365 E3 O A3, puede unirse al programa de vista previa.* |
| Requisitos de los exploradores | Microsoft Edge <br/> Versión 11 de Internet Explorer <br/> Google Chrome |
| Sistemas operativos | Windows 10, versión 1709 o posterior <br/>macOS: 11.5 (Big Sur), 10.15.7 (Catalina) o 10.14.6 (Mojave) <br/>iOS <br/>Sistema operativo Android  |
| Datacenter | Una de las siguientes ubicaciones de centro de datos: <br/>- Unión Europea <br/>- Reino Unido <br/>- Estados Unidos |


## <a name="plan-your-deployment"></a>Planear la implementación

Al planear la implementación, puede elegir entre varias arquitecturas y métodos de implementación diferentes. Cada organización es única, por lo que tiene varias opciones que tener en cuenta, como se muestra en la tabla siguiente: <br/><br/>

| Método | Descripción |
|:---|:---|
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (incluido en Microsoft Endpoint Manager) | Usar Intune para administrar puntos de conexión en un entorno nativo de la nube |
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Configuration Manager](/mem/configmgr/core/understand/introduction) (incluidos en Microsoft Endpoint Manager) | Usar Intune y Configuration Manager para administrar puntos de conexión y cargas de trabajo que abarcan un entorno local y de nube |
| [Configuration Manager](/mem/configmgr/core/understand/introduction) | Usar Configuration Manager para proteger los puntos de conexión locales con la potencia basada en la nube de Defender for Endpoint |
| Script local descargado desde el Microsoft 365 Defender Portal | Usar scripts locales en puntos de conexión para ejecutar un piloto o incorporar solo unos pocos dispositivos |

Para obtener más información sobre las opciones de implementación, consulte [Plan your Defender for Endpoint deployment](deployment-strategy.md). Y, descargue el siguiente póster: 

[:::image type="content" source="../../media/defender-endpoint/mde-deployment-strategy.png" alt-text="Miniatura del póster de estrategia de implementación":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)

**[Obtener el póster de implementación](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)**

> [!TIP]
> Para obtener información más detallada acerca de la planeación de la implementación, vea [Plan your Microsoft Defender for Endpoint deployment](deployment-strategy.md).

## <a name="set-up-your-tenant-environment"></a>Configurar el entorno de inquilino

La configuración del entorno de inquilino incluye tareas, como:

- Comprobar las licencias
- Configuración del espacio empresarial
- Configuración de la configuración de proxy (solo si es necesario)
- Asegurarse de que los sensores funcionan correctamente e informar de datos a Defender para endpoint 

Estas tareas se incluyen en la fase de configuración de Defender para endpoint. Consulte [Configurar Defender para endpoint](production-deployment.md).

## <a name="assign-roles-and-permissions"></a>Asignar roles y permisos

Para tener acceso al portal de Microsoft 365 Defender, configure la configuración de Defender para Endpoint o realice tareas, como realizar acciones de respuesta en las amenazas detectadas, deben asignarse los permisos adecuados. Defender para endpoint usa [roles integrados dentro de Azure Active Directory](/azure/active-directory/roles/permissions-reference). 

Microsoft recomienda asignar a los usuarios solo el nivel de permiso que necesitan para realizar sus tareas. Puede asignar permisos mediante la administración de permisos básicos o mediante el [control de](rbac.md) acceso basado en roles (RBAC). 

- Con la administración de permisos básicos, los administradores globales y los administradores de seguridad tienen acceso completo, mientras que los lectores de seguridad tienen acceso de solo lectura.
- Con RBAC, puede establecer permisos más granulares a través de más roles. Por ejemplo, puede tener lectores de seguridad, operadores de seguridad, administradores de seguridad, administradores de puntos de conexión y mucho más.


En la tabla siguiente se describen los roles clave que se deben tener en cuenta para Defender for Endpoint en su organización: <br/><br/>

| Función | Descripción |
|:---|:---|
| Administradores globales (también denominados administradores globales) <br/><br/> *Como práctica recomendada, limite el número de administradores globales.* | Los administradores globales pueden realizar todo tipo de tareas. La persona que se ha registrado en su empresa para Microsoft 365 o para Microsoft Defender para el plan de extremo 1 es un administrador global de forma predeterminada. <br/><br/> Los administradores globales pueden acceder o cambiar la configuración en todos Microsoft 365 portales, como: <br/>- El Centro de administración de Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) <br/>- Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) ) <br/>- Microsoft Endpoint Manager centro de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) )  |
| Administradores de seguridad (también denominados administradores de seguridad) | Los administradores de seguridad pueden realizar tareas de operador de seguridad más las siguientes tareas: <br/>- Supervisar directivas relacionadas con la seguridad <br/>- Administrar alertas y amenazas de seguridad <br/>- Ver informes |
| Operador de seguridad | Los operadores de seguridad pueden realizar tareas de lector de seguridad además de las siguientes tareas: <br/>- Ver información sobre las amenazas detectadas <br/>- Investigar y responder a las amenazas detectadas  |
| Lector de seguridad | Los lectores de seguridad pueden realizar las siguientes tareas: <br/>- Ver directivas relacionadas con la seguridad en Microsoft 365 servicios <br/>- Ver alertas y amenazas de seguridad <br/>- Ver informes  |


> [!TIP]
> Para obtener más información acerca de los roles en Azure Active Directory, vea Asignar roles de administrador y no administrador a usuarios [con Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Y, más información sobre los roles de Defender para endpoint, vea [Control de acceso basado en roles](prepare-deployment.md#role-based-access-control).

## <a name="onboard-to-defender-for-endpoint"></a>Incorporación a Defender para endpoint

Cuando esté listo para incorporar los puntos de conexión de su organización, puede elegir entre varios métodos, como se muestra en la tabla siguiente: <br/><br/>

|Sistema operativo Endpoint | Métodos de incorporación|
|---|---|
| Windows 10 | [Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Administrador de dispositivos móviles](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts VDI](configure-endpoints-vdi.md)  |
| macOS | [Scripts locales](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móviles](mac-install-with-other-mdm.md) |
| iOS |[Basado en aplicaciones](ios-install.md) |
| Android | [Microsoft Endpoint Manager](android-intune.md) |

A continuación, continúe con la configuración de la protección de última generación y las capacidades de reducción de superficie de ataque.

## <a name="configure-next-generation-protection"></a>Configurar protección de última generación

Se recomienda usar [Microsoft Endpoint Manager](/mem) para administrar los dispositivos y la configuración de seguridad de la organización, como se muestra en la siguiente imagen:
 
:::image type="content" source="../../media/mde-p1/endpoint-policies.png" alt-text="Directivas de seguridad de extremo en MEM":::

Para configurar la protección de próxima generación en Microsoft Endpoint Manager, siga estos pasos:

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Seleccione **Endpoint security**  >  **Antivirus** y, a continuación, seleccione una directiva existente. (Si no tiene una directiva existente, cree una directiva nueva).

3. Establece o cambia las opciones de configuración del antivirus. ¿Necesita ayuda? Consulte los siguientes recursos: <br/>

   - [Configuración para Windows 10 Antivirus de Microsoft Defender directiva en Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)
   - [Configurar Defender para endpoint en características de iOS](ios-configure-features.md)

4. Cuando haya terminado de especificar la configuración, elija **Revisar y guardar**.

## <a name="configure-your-attack-surface-reduction-capabilities"></a>Configurar las capacidades de reducción de superficie de ataque

La reducción de superficie de ataque se trata de reducir los lugares y formas en que la organización está abierta al ataque. Defender for Endpoint Plan 1 incluye varias características y funcionalidades que te ayudarán a reducir las superficies de ataque en todos los puntos de conexión. Estas características y funcionalidades se enumeran en la tabla siguiente: <br/><br/>

| Característica/funcionalidad | Descripción |
|:---|:---|
| [Reglas de la reducción de la superficie expuesta a ataques](#attack-surface-reduction-rules) | Configure las reglas de reducción de superficie de ataque para restringir los comportamientos de riesgo basados en software y ayudar a mantener la organización segura. Las reglas de reducción de superficie de ataque se aplican a determinados comportamientos de software, como<br/>- Iniciar archivos ejecutables y scripts que intentan descargar o ejecutar archivos <br/>- Ejecución de scripts ofuscados o sospechosos <br/>- Realizar comportamientos que las aplicaciones normalmente no inician durante el trabajo diario normal <br/><br/>Estos comportamientos de software a veces se ven en aplicaciones legítimas. Sin embargo, estos comportamientos suelen considerarse riesgosos porque los atacantes suelen abusar de ellos a través del malware.  |
| [Mitigación de ransomware](#ransomware-mitigation) | Configure la mitigación de ransomware configurando el acceso controlado a carpetas, lo que ayuda a proteger los datos valiosos de su organización frente a amenazas y aplicaciones malintencionadas, como ransomware. | 
| [Control de dispositivos](#device-control) | Configure las opciones de control de dispositivos para que la organización permita o bloquee dispositivos extraíbles (como unidades USB). | 
| [Protección de red](#network-protection) | Configure la protección de red para evitar que las personas de su organización utilicen aplicaciones que tienen acceso a dominios peligrosos o contenido malintencionado en Internet. |
| [Protección web](#web-protection) | Configure la protección contra amenazas web para proteger los dispositivos de su organización de sitios de suplantación de identidad(phishing), sitios de vulnerabilidad de seguridad y otros sitios que no son de confianza o de baja reputación. Configurar el filtrado de contenido web para realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido (como Ocio, Ancho de banda alto, contenido para adultos o Responsabilidad legal). |
| [Firewall de red](#network-firewall) | Configure el firewall de red con reglas que determinen qué tráfico de red puede entrar o salir de los dispositivos de la organización. |
| [Control de la aplicación](#application-control)  | Configure las reglas de control de aplicaciones si desea permitir que solo se ejecuten aplicaciones y procesos de confianza en los dispositivos Windows confianza.    |

### <a name="attack-surface-reduction-rules"></a>Reglas de reducción de la superficie expuesta a ataques

Las reglas de reducción de superficie de ataque están disponibles en dispositivos que ejecutan Windows. Se recomienda usar Microsoft Endpoint Manager, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Reglas de reducción de superficie de ataque en Microsoft Endpoint Manager":::

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Elija **Endpoint security** Attack surface  >  **reduction**+ Create  >  **policy**.

3. En **Plataforma**, seleccione **Windows 10 y versiones posteriores**.

4. En **Perfil**, seleccione **Reglas de reducción de** superficie de ataque y, a continuación, elija **Crear**.

5. En la **pestaña Conceptos** básicos, especifique un nombre y una descripción para la directiva y, a continuación, elija **Siguiente**.

6. En la **pestaña Configuración,** **expande Reglas de reducción de superficie de ataque**.

7. Especifique la configuración de cada regla y, a continuación, **elija Siguiente**. (Para obtener más información acerca de lo que hace cada regla, consulte [Reglas de reducción de superficie de ataque](attack-surface-reduction.md).) 

8. En la **pestaña Etiquetas de** ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar** etiquetas de ámbito y, a continuación, seleccione las etiquetas que desee usar. A continuación, **elija Siguiente**. 
   
   Para obtener más información acerca de las etiquetas de ámbito, vea [Use role-based access control (RBAC) and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags).

9. En la **pestaña Asignaciones,** especifique los usuarios y grupos a los que se debe aplicar la directiva y, a continuación, **elija Siguiente**. (Para obtener más información acerca de las asignaciones, consulta [Asignar perfiles](/mem/intune/configuration/device-profile-assign)de usuario y dispositivo en Microsoft Intune .)

10. En la **pestaña Revisar + crear,** revise la configuración y, a continuación, elija **Crear**.

> [!TIP]
> Para obtener más información sobre las reglas de reducción de superficie de ataque, consulta los siguientes recursos:
> - [Usar reglas de reducción de la superficie expuesta a ataques para evitar la infección de malware](attack-surface-reduction.md)
> - [Ver la lista de reglas de reducción de superficie de ataque](attack-surface-reduction-rules.md)
> - [Personalizar las reglas de la reducción de superficie expuesta a ataques](customize-attack-surface-reduction.md)

### <a name="ransomware-mitigation"></a>Mitigación de ransomware

Obtienes mitigación de ransomware a través [del acceso controlado a](controlled-folders.md#what-is-controlled-folder-access)carpetas, lo que solo permite que las aplicaciones de confianza obtengan acceso a carpetas protegidas en los puntos de conexión. 

Se recomienda usar Microsoft Endpoint Manager para configurar el acceso controlado a carpetas.

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Directivas ASR en Microsoft Endpoint Manager":::

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión. 

2. Selecciona **Seguridad de punto** de conexión y, a continuación, selecciona **Reducción de superficie de ataque.**

3. Elija **+ Crear directiva**. 

4. Para **Plataforma**, seleccione **Windows 10 y posteriores,** y **para Perfil**, seleccione Reglas **de reducción de superficie de ataque**. Después, haga clic en **Crear**. 

5. En la **pestaña Conceptos** básicos, asigne un nombre a la directiva y agregue una descripción. Seleccione **Siguiente**. 

6. En la **pestaña Configuración,** en la sección Reglas de reducción de **superficie** de ataque, desplácese hacia abajo hasta la parte inferior. En la **lista desplegable Habilitar** protección de carpetas, seleccione **Habilitar**. Opcionalmente, puede especificar estas otras opciones:

   - Junto a **Lista de carpetas adicionales** que deben protegerse, seleccione el menú desplegable y, a continuación, agregue carpetas que necesiten protegerse.
   - Junto a **Lista de aplicaciones que tienen** acceso a carpetas protegidas, selecciona el menú desplegable y luego agrega aplicaciones que deben tener acceso a carpetas protegidas.
   - Junto **a** Excluir archivos y rutas de acceso de las reglas de reducción de superficie de ataque, selecciona el menú desplegable y, a continuación, agrega los archivos y rutas de acceso que deben excluirse de las reglas de reducción de superficie de ataque.

   A continuación, elija **Siguiente**.

7. En la **pestaña Etiquetas de** ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar** etiquetas de ámbito y, a continuación, seleccione las etiquetas que desee usar. A continuación, **elija Siguiente**. 
   
   Para obtener más información acerca de las etiquetas de ámbito, vea [Use role-based access control (RBAC) and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags).

8. En la **pestaña Asignaciones,** seleccione **Agregar todos los usuarios y** + Agregar **todos** los dispositivos y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

9. En la **pestaña Revisar y crear,** revise la configuración de la directiva y, a continuación, elija **Crear**. La directiva se aplicará a los puntos de conexión que se incorporaron a Defender for Endpoint en breve.

### <a name="device-control"></a>Control de dispositivos

Puede configurar Defender for Endpoint para bloquear o permitir dispositivos y archivos extraíbles en dispositivos extraíbles. Se recomienda usar Microsoft Endpoint Manager para configurar la configuración del control del dispositivo.

:::image type="content" source="../../media/mde-p1/mem-admintemplates.png" alt-text="Microsoft Endpoint Manager administrativas":::

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión. 

2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.

3. Para **Plataforma**, seleccione **Windows 10 y posteriores,** y para Tipo de **perfil**, seleccione **Plantillas**. 

   En **Nombre de plantilla,** seleccione **Plantillas administrativas** y, a continuación, elija **Crear**. 

4. En la **pestaña Conceptos** básicos, asigne un nombre a la directiva y agregue una descripción. Seleccione **Siguiente**. 

5. En la **pestaña Configuración,** seleccione **Todos los Configuración**. A continuación, en el cuadro de búsqueda, escriba `Removable` para ver toda la configuración que pertenece a dispositivos extraíbles.

6. Seleccione un elemento de la lista, como **All Removable Storage classes: Deny all access**, para abrir su panel desplegable. El control desplegable de cada configuración explica qué sucede cuando está habilitada, deshabilitada o no configurada. Seleccione una configuración y, a continuación, **elija Aceptar**. 

7. Repita el paso 6 para cada configuración que desee configurar. A continuación, elija **Siguiente**.

8. En la **pestaña Etiquetas de** ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar** etiquetas de ámbito y, a continuación, seleccione las etiquetas que desee usar. A continuación, **elija Siguiente**. 
   
   Para obtener más información acerca de las etiquetas de ámbito, vea [Use role-based access control (RBAC) and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags).

9. En la **pestaña Asignaciones,** seleccione **Agregar todos los usuarios y** + Agregar **todos** los dispositivos y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

10. En la **pestaña Revisar y crear,** revise la configuración de la directiva y, a continuación, elija **Crear**. La directiva se aplicará a los puntos de conexión que se incorporaron a Defender for Endpoint en breve.

> [!TIP]
> Para obtener más información, [vea How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).

### <a name="network-protection"></a>Protección de red

Con la protección de red, puede ayudar a proteger su organización contra dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet. Se recomienda usar Microsoft Endpoint Manager para activar la protección de red.

:::image type="content" source="../../media/mde-p1/mem-endpointprotectionprofile.png" alt-text="Perfil de protección de extremos en Microsoft Endpoint Manager":::

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión. 

2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.

3. Para **Plataforma**, seleccione **Windows 10 y posteriores,** y para Tipo de **perfil**, seleccione **Plantillas**. 

   En **Nombre de plantilla,** seleccione **Protección de extremo** y, a continuación, elija **Crear**. 

4. En la **pestaña Conceptos** básicos, asigne un nombre a la directiva y agregue una descripción. Seleccione **Siguiente**. 

5. En la **pestaña Configuración,** expanda **Protección contra vulnerabilidades de seguridad de Microsoft Defender** y, a continuación, expanda **Filtrado de red**.

   Establezca **La protección de red** en **Habilitar**. (Puede elegir auditoría alternativamente **para** ver cómo funcionará la protección de red en el entorno al principio).

   A continuación, elija **Siguiente**.

6. En la **pestaña Asignaciones,** seleccione **Agregar todos los usuarios y** + Agregar **todos** los dispositivos y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

7. En la **pestaña Reglas de aplicabilidad,** configure una regla. El perfil que configures se aplicará solo a dispositivos que cumplan los criterios combinados que especifiques. 

   Por ejemplo, puede optar por asignar la directiva a puntos de conexión que solo ejecutan una determinada edición del sistema operativo.

   A continuación, elija **Siguiente**. 

8. En la **pestaña Revisar y crear,** revise la configuración de la directiva y, a continuación, elija **Crear**. La directiva se aplicará a los puntos de conexión que se incorporaron a Defender for Endpoint en breve.

> [!TIP]
> Puede usar otros métodos, como Windows PowerShell o directiva de grupo, para habilitar la protección de red. Para obtener más información, vea [Activar la protección de red](enable-network-protection.md).

### <a name="web-protection"></a>Protección web

Con la protección web, puede proteger los dispositivos de su organización frente a amenazas web y contenido no deseado. La protección web incluye [protección contra amenazas web](#configure-web-threat-protection) y filtrado de contenido [web](#configure-web-content-filtering) (versión preliminar). Configure ambos conjuntos de funcionalidades. Se recomienda usar Microsoft Endpoint Manager para configurar la configuración de la protección web.

#### <a name="configure-web-threat-protection"></a>Configurar la protección contra amenazas web

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.
 
2. Elija **Endpoint security** Attack surface  >  **reduction** y, a continuación, elija + Create **policy**.

3. Seleccione una plataforma, como Windows 10 y **posterior,** seleccione el perfil de protección **web** y, a continuación, **elija Crear**. 

4. En la **pestaña Conceptos** básicos, especifique un nombre y una descripción y, a continuación, elija **Siguiente**.

5. En la **pestaña Configuración,** expanda **Protección web**, especifique la configuración de la tabla siguiente y, a continuación, **elija Siguiente**. <br/><br/>

   | Setting | Recomendación |
   |:---|:---|
   | **Habilitar la protección de red** | Se establece en **Habilitado**. Impide que los usuarios visiten sitios o dominios malintencionados. <br/><br/>Como alternativa, puede establecer la protección de red en **modo auditoría** para ver cómo funcionará en su entorno. En el modo de auditoría, la protección de red no impide que los usuarios visiten sitios o dominios, pero sí realiza un seguimiento de las detecciones como eventos. |
   | **Requerir SmartScreen para Microsoft Edge (versión anterior)** | Se establece en **Sí**. Ayuda a proteger a los usuarios de posibles estafas de suplantación de identidad (phishing) y software malintencionado. |
   | **Bloquear el acceso a sitios malintencionados** | Se establece en **Sí**. Evita que los usuarios omitan advertencias sobre sitios potencialmente malintencionados. |
   | **Bloquear la descarga de archivos noverificados** | Se establece en **Sí**. Evita que los usuarios omitan las advertencias y descarguen archivos no registrados. |

6. En la **pestaña Etiquetas de** ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar** etiquetas de ámbito y, a continuación, seleccione las etiquetas que desee usar. A continuación, **elija Siguiente**. 
   
   Para obtener más información acerca de las etiquetas de ámbito, vea [Use role-based access control (RBAC) and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags).

7. En la **pestaña Asignaciones,** especifique los usuarios y dispositivos para recibir la directiva de protección web y, a continuación, elija **Siguiente**.

8. En la **pestaña Revisar + crear,** revise la configuración de la directiva y, a continuación, elija **Crear**.

> [!TIP]
> Para obtener más información sobre la protección contra amenazas web, vea [Proteger su organización contra amenazas web.](web-threat-protection.md)

#### <a name="configure-web-content-filtering"></a>Configurar el filtrado de contenido web

> [!NOTE]
> El filtrado de contenido web está actualmente en versión preliminar.

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com/](https://security.microsoft.com/) ) e inicie sesión.

2. Elija **Configuración**  >  **endpoints**.

3. En **Reglas**, elija **Filtrado de contenido web** y, a continuación, elija + Agregar **directiva**.

4. En el control desplegable Agregar **directiva,** en la **pestaña General,** especifique un nombre para la directiva y, a continuación, elija **Siguiente**.

5. En categorías **bloqueadas,** seleccione una o varias categorías que desee bloquear y, a continuación, elija **Siguiente**.

6. En la **pestaña Ámbito,** selecciona los grupos de dispositivos que quieres recibir esta directiva y, a continuación, elige **Siguiente**.

7. En la **pestaña Resumen,** revise la configuración de la directiva y, a continuación, **elija Guardar**.

> [!TIP]
> Para obtener más información sobre cómo configurar el filtrado de contenido web, consulte [Web content filtering](web-content-filtering.md).

### <a name="network-firewall"></a>Firewall de red

El firewall de red ayuda a reducir el riesgo de amenazas de seguridad de red. El equipo de seguridad puede establecer reglas que determinen qué tráfico puede fluir hacia o desde los dispositivos de la organización. Se recomienda usar Microsoft Endpoint Manager para configurar el firewall de red. 

:::image type="content" source="../../media/mde-p1/mem-firewallpolicy.png" alt-text="Directiva de firewall en Microsoft Endpoint Manager":::

Para configurar la configuración básica del firewall, siga estos pasos:

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Elija **Firewall de seguridad**  >  **de** extremo y, a continuación, elija + Crear **directiva**.

3. Seleccione una plataforma, como **Windows 10** y posterior, seleccione el perfil firewall de **Microsoft Defender** y, a continuación, **elija Crear**. 

4. En la **pestaña Conceptos** básicos, especifique un nombre y una descripción y, a continuación, elija **Siguiente**.

5. Expanda **Firewall de Microsoft Defender** y, a continuación, desplácese hacia abajo hasta la parte inferior de la lista.

6. Establezca cada una de las siguientes opciones en **Sí**:

   - **Activar Firewall de Microsoft Defender para redes de dominio** 
   - **Activar firewall de Microsoft Defender para redes privadas**
   - **Activar firewall de Microsoft Defender para redes públicas**
   
   Revise la lista de opciones de configuración en cada una de las redes de dominio, redes privadas y redes públicas. Puede dejarlos establecidos en **No configurados** o cambiarlos para que se adapten a las necesidades de su organización.

   A continuación, elija **Siguiente**.

7. En la **pestaña Etiquetas de** ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar** etiquetas de ámbito y, a continuación, seleccione las etiquetas que desee usar. A continuación, **elija Siguiente**. 
   
   Para obtener más información acerca de las etiquetas de ámbito, vea [Use role-based access control (RBAC) and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags).

8. En la **pestaña Asignaciones,** seleccione **Agregar todos los usuarios y** + Agregar **todos** los dispositivos y, a continuación, elija **Siguiente**. (También puede especificar grupos específicos de usuarios o dispositivos).

9. En la **pestaña Revisar + crear,** revise la configuración de la directiva y, a continuación, elija **Crear**.

> [!TIP]
> La configuración del firewall es detallada y puede parecer compleja. Consulte [Procedimientos recomendados para configurar Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/best-practices-configuring).

### <a name="application-control"></a>Control de la aplicación

Windows Defender control de aplicaciones (WDAC) ayuda a proteger los puntos de conexión Windows, ya que solo permite que se ejecuten aplicaciones y procesos de confianza. La mayoría de las organizaciones usaban una implementación por fases de WDAC. Es decir, la mayoría de las organizaciones no lanzan WDAC en todos los Windows en un primer momento. De hecho, en función de si los puntos de conexión Windows de la organización están totalmente administrados, administrados ligeramente o "Traer su propio dispositivo", es posible que implemente WDAC en todos o algunos puntos de conexión.

Para ayudarle con la planeación de la implementación de WDAC, consulte los siguientes recursos:

- [Control de aplicaciones para Windows](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender de diseño de directivas de control de aplicaciones](/windows/security/threat-protection/windows-defender-application-control/understand-windows-defender-application-control-policy-design-decisions)

- [Windows Defender de control de aplicaciones en diferentes escenarios: tipos de dispositivos](/windows/security/threat-protection/windows-defender-application-control/types-of-devices)

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha pasado por el proceso de configuración y configuración, el siguiente paso es empezar a usar Defender para endpoint. 

- [Introducción a Defender for Endpoint Plan 1](mde-plan1-getting-started.md)