---
title: Incorporación mediante Microsoft Endpoint Configuration Manager
description: Obtenga información sobre cómo incorporarse a Microsoft Defender para endpoint mediante Microsoft Endpoint Configuration Manager
keywords: incorporación, configuración, implementación, administrador de configuración de puntos de conexión, Microsoft Defender para endpoint, creación de colecciones, respuesta de detección de puntos de conexión, protección de próxima generación, reducción de superficie de ataque, administrador de configuración de puntos de conexión de Microsoft
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b8847fb9132ee037a3103bf86aabd14d21fb482f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469435"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Incorporación mediante Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este artículo forma parte de la guía de implementación y actúa como un método de incorporación de ejemplo.

En el [tema Planeación](deployment-strategy.md) , se proporcionaron varios métodos para incorporar dispositivos al servicio. En este tema se trata la arquitectura de administración en colaboración.

:::image type="content" source="images/co-management-architecture.png" alt-text="La arquitectura nativa de la nube" lightbox="images/co-management-architecture.png":::
*Diagrama de arquitecturas de entorno*

Aunque Defender para endpoint admite la incorporación de varios puntos de conexión y herramientas, este artículo no los cubre. Para obtener información sobre la incorporación general con otras herramientas y métodos de implementación compatibles, consulte [Onboarding overview](onboarding.md).

En este tema se guía a los usuarios en:

- Paso 1: Incorporación de Windows dispositivos al servicio
- Paso 2: Configuración de las capacidades de Defender para puntos de conexión

Esta guía de incorporación le llevará a través de los siguientes pasos básicos que debe seguir al usar Microsoft Endpoint Configuration Manager:

- **Crear una colección en Microsoft Endpoint Configuration Manager**
- **Configurar Las capacidades de Microsoft Defender para puntos de conexión mediante Microsoft Endpoint Configuration Manager**

> [!NOTE]
> Solo Windows dispositivos están cubiertos en esta implementación de ejemplo.

## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Paso 1: Incorporación Windows dispositivos con Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Creación de colecciones

Para incorporar Windows dispositivos con Microsoft Endpoint Configuration Manager, la implementación puede dirigirse a una colección existente o se puede crear una nueva colección para pruebas.

La incorporación mediante herramientas como la directiva de grupo o el método manual no instala ningún agente en el sistema.

Dentro de Microsoft Endpoint Configuration Manager consola, el proceso de incorporación se configurará como parte de la configuración de cumplimiento dentro de la consola.

Cualquier sistema que reciba esta configuración necesaria mantendrá esa configuración mientras el cliente de Configuration Manager siga recibiendo esta directiva desde el punto de administración.

Siga los pasos siguientes para incorporar puntos de conexión mediante Microsoft Endpoint Configuration Manager.

1. En Microsoft Endpoint Configuration Manager consola, vaya a **Assets and Compliance \> Overview \> Device Collections**.

    :::image type="content" source="images/configmgr-device-collections.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 1" lightbox="images/configmgr-device-collections.png":::

2. Haga clic con el **botón secundario en Colección de** dispositivos **y seleccione Crear colección de dispositivos**.

    :::image type="content" source="images/configmgr-create-device-collection.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 2" lightbox="images/configmgr-create-device-collection.png":::

3. Proporcione una **colección Name** y **Limiting y**, a continuación, seleccione **Siguiente**.

    :::image type="content" source="images/configmgr-limiting-collection.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 3" lightbox="images/configmgr-limiting-collection.png":::

4. Seleccione **Agregar regla y** elija **Regla de consulta**.

    :::image type="content" source="images/configmgr-query-rule.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 4" lightbox="images/configmgr-query-rule.png":::

5. Haga **clic en Siguiente** en el **Asistente para pertenencia directa** y haga clic en **Editar instrucción query**.

    :::image type="content" source="images/configmgr-direct-membership.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 5" lightbox="images/configmgr-direct-membership.png":::

6. Seleccione **Criterios** y, a continuación, elija el icono de estrella.

    :::image type="content" source="images/configmgr-criteria.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 6" lightbox="images/configmgr-criteria.png":::

7. Mantenga el tipo de criterio como valor **simple**, elija dónde como Sistema operativo **:** número de compilación, operador igual o mayor que y valor **14393** y haga clic en **Aceptar**.

    :::image type="content" source="images/configmgr-simple-value.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 7" lightbox="images/configmgr-simple-value.png":::

8. Seleccione **Siguiente** y **Cerrar**.

    :::image type="content" source="images/configmgr-membership-rules.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 8" lightbox="images/configmgr-membership-rules.png":::

9. Seleccione **Siguiente**.

    :::image type="content" source="images/configmgr-confirm.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 9" lightbox="images/configmgr-confirm.png":::

Después de completar esta tarea, ahora tienes una colección de dispositivos con todos los Windows en el entorno.

## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Paso 2: Configurar Microsoft Defender para las funcionalidades de punto de conexión

En esta sección se le guía en la configuración de las siguientes funcionalidades Microsoft Endpoint Configuration Manager en Windows dispositivos:

- [**Detección y respuesta de puntos de conexión**](#endpoint-detection-and-response)
- [**Protección de última generación**](#next-generation-protection)
- [**Reducción de la superficie expuesta a ataques**](#attack-surface-reduction)

### <a name="endpoint-detection-and-response"></a>EDR

#### <a name="windows-10-and-windows-11"></a>Windows 10 y Windows 11

Desde el portal `.onboarding` de Microsoft 365 Defender es posible descargar la directiva que se puede usar para crear la directiva en System Center Configuration Manager e implementarla en Windows 10 y Windows 11 dispositivos.

1. En un <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender</a>, [seleccione Configuración y,](https://security.microsoft.com/preferences2/onboarding) a continuación, Incorporación.

2. En Método de implementación, seleccione la versión admitida de **Microsoft Endpoint Configuration Manager**.

    :::image type="content" source="images/mdatp-onboarding-wizard.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 10" lightbox="images/mdatp-onboarding-wizard.png":::

3. Seleccione **Descargar paquete**.

   :::image type="content" source="images/mdatp-download-package.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 11" lightbox="images/mdatp-download-package.png":::

4. Guarde el paquete en una ubicación accesible.
5. En Microsoft Endpoint Configuration Manager, vaya a: **Assets and Compliance > Overview > Endpoint Protection > Directivas de ATP de Microsoft Defender**.

6. Haz clic con el botón **secundario en Directivas de ATP de Microsoft Defender** y **selecciona Crear directiva de ATP de Microsoft Defender**.

    :::image type="content" source="images/configmgr-create-policy.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 12" lightbox="images/configmgr-create-policy.png":::

7. Escriba el nombre y la descripción, compruebe **que la incorporación** está seleccionada y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="images/configmgr-policy-name.png" alt-text="El Microsoft Endpoint Configuration Manager de Microsoft Endpoint Configuration Manager 13" lightbox="images/configmgr-policy-name.png":::

8. Haga clic en **Examinar**.

9. Vaya a la ubicación del archivo descargado desde el paso 4 anterior.

10. Haga clic en **Siguiente**.
11. Configure el agente con los ejemplos adecuados (**ninguno** o **todos los tipos de archivo**).

    :::image type="content" source="images/configmgr-config-settings.png" alt-text="Las opciones de configuración1" lightbox="images/configmgr-config-settings.png":::

12. Seleccione la telemetría adecuada (**Normal** o **Expedited**) y, a continuación, haga clic en **Siguiente**.

    :::image type="content" source="images/configmgr-telemetry.png" alt-text="Las opciones de configuración2" lightbox="images/configmgr-telemetry.png":::

13. Compruebe la configuración y, a continuación, **haga clic en Siguiente**.

    :::image type="content" source="images/configmgr-verify-configuration.png" alt-text="Las opciones de configuración3" lightbox="images/configmgr-verify-configuration.png":::

14. Haga **clic en** Cerrar cuando se complete el Asistente.

15. En la Microsoft Endpoint Configuration Manager, haga clic con el botón secundario en la directiva defender para endpoint que acaba de crear y seleccione **Implementar**.

    :::image type="content" source="images/configmgr-deploy.png" alt-text="Las opciones de configuración4" lightbox="images/configmgr-deploy.png":::

16. En el panel derecho, seleccione la colección creada anteriormente y haga clic en **Aceptar**.

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="Configuración5" lightbox="images/configmgr-select-collection.png":::

#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Versiones anteriores de Windows Client (Windows 7 y Windows 8.1)

Siga los pasos siguientes para identificar el id. de área de trabajo de Defender for Endpoint y la clave de área de trabajo, que serán necesarios para la incorporación de versiones anteriores de Windows.

1. En un <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender</a>, seleccione **Configuración** \> **incorporación** \> de puntos de **conexión (en** **Administración de dispositivos**).

2. En sistema operativo, **elija Windows 7 SP1 y 8.1**.

3. Copie el **identificador del área de trabajo** **y la clave de área de trabajo** y guárdelos. Se usarán más adelante en el proceso.

   :::image type="content" source="images/91b738e4b97c4272fd6d438d8c2d5269.png" alt-text="Proceso de incorporación" lightbox="images/91b738e4b97c4272fd6d438d8c2d5269.png":::

4. Instale el Microsoft Monitoring Agent (MMA).

   MMA actualmente (a partir de enero de 2019) se admite en los siguientes sistemas Windows operativos:

   - SKU de servidor: Windows Server 2008 SP1 o versiones posteriores
   - SKU de cliente: Windows 7 SP1 y versiones posteriores

   El agente mma tendrá que instalarse en Windows dispositivos. Para instalar el agente, algunos sistemas tendrán que descargar la actualización [](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) para la experiencia del cliente y la telemetría de diagnóstico para recopilar los datos con MMA. Estas versiones del sistema incluyen, pero no pueden limitarse a:

   - Windows 8.1
   - Windows 7
   - Windows Server 2016
   - Windows Server 2012 R2
   - Windows Server 2008 R2

   Específicamente, para Windows 7 SP1, deben instalarse las siguientes revisiones:

   - Instalar [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
   - Instale .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) **o** [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework). No instale ambos en el mismo sistema.

5. Si usa un proxy para conectarse a Internet, consulte la sección Configurar opciones de proxy.

Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.

### <a name="next-generation-protection"></a>Protección de última generación

El Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona una protección de última generación para equipos de escritorio, equipos portátiles y servidores.

1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** y elija **Create Antimalware Policy**.

   :::image type="content" source="images/9736e0358e86bc778ce1bd4c516adb8b.png" alt-text="La directiva de antimalware" lightbox="images/9736e0358e86bc778ce1bd4c516adb8b.png":::

2. Seleccione **Exámenes programados****, Configuración** del **examen, Acciones** predeterminadas, Protección en tiempo **real****, Configuración** de exclusión **, Opciones** avanzadas, Invalidaciones de **amenazas, Servicio** de protección en la nube y Actualizaciones de inteligencia **de seguridad** y **elija Aceptar**.

   :::image type="content" source="images/1566ad81bae3d714cc9e0d47575a8cbd.png" alt-text="Panel de protección de próxima generación1" lightbox="images/1566ad81bae3d714cc9e0d47575a8cbd.png":::

    En determinados sectores o en algunos clientes empresariales selectos puede haber necesidades específicas sobre cómo se configura Antivirus.

    [Examen rápido frente a examen completo y examen personalizado](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Para obtener más información, [vea Seguridad de Windows marco de configuración.](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    :::image type="content" source="images/cd7daeb392ad5a36f2d3a15d650f1e96.png" alt-text="Panel de protección de próxima generación2" lightbox="images/cd7daeb392ad5a36f2d3a15d650f1e96.png":::

    :::image type="content" source="images/36c7c2ed737f2f4b54918a4f20791d4b.png" alt-text="Panel de protección de próxima generación3" lightbox="images/36c7c2ed737f2f4b54918a4f20791d4b.png":::

    :::image type="content" source="images/a28afc02c1940d5220b233640364970c.png" alt-text="Panel de protección de próxima generación4" lightbox="images/a28afc02c1940d5220b233640364970c.png":::

    :::image type="content" source="images/5420a8790c550f39f189830775a6d4c9.png" alt-text="Panel de protección de próxima generación5" lightbox="images/5420a8790c550f39f189830775a6d4c9.png":::

    :::image type="content" source="images/33f08a38f2f4dd12a364f8eac95e8c6b.png" alt-text="Panel de protección de próxima generación6" lightbox="images/33f08a38f2f4dd12a364f8eac95e8c6b.png":::

    :::image type="content" source="images/41b9a023bc96364062c2041a8f5c344e.png" alt-text="Panel de protección de próxima generación7" lightbox="images/41b9a023bc96364062c2041a8f5c344e.png":::

    :::image type="content" source="images/945c9c5d66797037c3caeaa5c19f135c.png" alt-text="Panel de protección de próxima generación8" lightbox="images/945c9c5d66797037c3caeaa5c19f135c.png":::

    :::image type="content" source="images/3876ca687391bfc0ce215d221c683970.png" alt-text="Panel de protección de próxima generación9" lightbox="images/3876ca687391bfc0ce215d221c683970.png":::

3. Haga clic con el botón secundario en la directiva antimalware recién creada y seleccione **Implementar**.

    :::image type="content" source="images/f5508317cd8c7870627cb4726acd5f3d.png" alt-text="Panel de protección de próxima generación10" lightbox="images/f5508317cd8c7870627cb4726acd5f3d.png":::

4. Dirigir la nueva directiva antimalware a la colección Windows y haga clic en **Aceptar**.

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="Panel de protección de próxima generación11" lightbox="images/configmgr-select-collection.png":::

Después de completar esta tarea, ahora ha configurado correctamente Antivirus de Windows Defender.

### <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

El pilar de reducción de superficie de ataque de Defender para endpoint incluye el conjunto de características que está disponible en Protección contra vulnerabilidades de seguridad. Reglas de reducción de superficie de ataque (ASR), Acceso controlado a carpetas, Protección de red y Protección contra vulnerabilidades de seguridad.

Todas estas características proporcionan un modo de auditoría y un modo de bloqueo. En el modo de auditoría no hay ningún impacto para el usuario final. Todo lo que hace es recopilar telemetría adicional y hacer que esté disponible en el portal Microsoft 365 Defender web. El objetivo con una implementación es mover paso a paso los controles de seguridad al modo de bloqueo.

Para establecer reglas ASR en modo auditoría:

1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** y elija **Create Exploit Guard Policy**.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="La Microsoft Endpoint Configuration Manager consola0" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. Selecciona **Reducción de superficie de ataque**.

3. Establece las reglas en **Auditar** y haz clic en **Siguiente**.

   :::image type="content" source="images/d18e40c9e60aecf1f9a93065cb7567bd.png" alt-text="La Microsoft Endpoint Configuration Manager consola1" lightbox="images/d18e40c9e60aecf1f9a93065cb7567bd.png":::

4. Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="La Microsoft Endpoint Configuration Manager consola2" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. Una vez creada la directiva, haga clic **en Cerrar**.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="La Microsoft Endpoint Configuration Manager consola3" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="La Microsoft Endpoint Configuration Manager consola4" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. Dirigir la directiva a la colección recién Windows y haga clic en **Aceptar**.

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="La Microsoft Endpoint Configuration Manager consola5" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Después de completar esta tarea, ahora ha configurado correctamente las reglas de ASR en el modo de auditoría.

A continuación se indican pasos adicionales para comprobar si las reglas ASR se aplican correctamente a los puntos de conexión. (Esto puede tardar unos minutos)

1. Desde un explorador web, vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>.

2. Seleccione **Administración de configuración** en el menú del lado izquierdo.

3. Haz **clic en Ir a la administración de superficies de** ataque en el panel Administración de superficie de ataque.

   :::image type="content" source="images/security-center-attack-surface-mgnt-tile.png" alt-text="Administración de superficie de ataque" lightbox="images/security-center-attack-surface-mgnt-tile.png":::

4. Haga clic **en la pestaña** Configuración en Informes de reglas de reducción de superficie de ataque. Muestra información general sobre la configuración de reglas ASR y el estado de las reglas ASR en cada dispositivo.

   :::image type="content" source="images/f91f406e6e0aae197a947d3b0e8b2d0d.png" alt-text="Informes de las reglas de reducción de superficie de ataque1" lightbox="images/f91f406e6e0aae197a947d3b0e8b2d0d.png":::

5. Haga clic en cada dispositivo para ver los detalles de configuración de las reglas de ASR.

   :::image type="content" source="images/24bfb16ed561cbb468bd8ce51130ca9d.png" alt-text="Informes de las reglas de reducción de superficie de ataque2" lightbox="images/24bfb16ed561cbb468bd8ce51130ca9d.png":::

Consulte [Optimizar la implementación y detecciones de reglas ASR](/microsoft-365/security/defender-endpoint/configure-machines-asr) para obtener más información.

#### <a name="set-network-protection-rules-in-audit-mode"></a>Establecer reglas de protección de red en modo auditoría

1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** y elija **Create Exploit Guard Policy**.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="El System Center Configuration Manager1" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. Seleccione **Protección de red**.

3. Establezca la configuración en **Auditar y** haga clic en **Siguiente**.

   :::image type="content" source="images/c039b2e05dba1ade6fb4512456380c9f.png" alt-text="El System Center Configuration Manager2" lightbox="images/c039b2e05dba1ade6fb4512456380c9f.png":::

4. Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="La directiva de Protección contra vulnerabilidades1" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. Una vez creada la directiva, haga clic en **Cerrar**.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="La directiva de Protección contra vulnerabilidades2" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="El Microsoft Endpoint Configuration Manager-1" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. Seleccione la directiva de la colección de Windows recién creada y elija **Aceptar**.

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="El Microsoft Endpoint Configuration Manager-2" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Después de completar esta tarea, ahora ha configurado correctamente Protección de red en modo auditoría.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Para establecer reglas de acceso controlado a carpetas en modo auditoría

1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and** **ComplianceOverview** >  >  **Endpoint Protection** >  **Windows Defender Exploit Guard** y, a continuación, elija **Crear directiva de protección contra vulnerabilidades de seguridad**.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="El Microsoft Endpoint Configuration Manager-3" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. Seleccione **Acceso controlado a carpetas**.

3. Establezca la configuración en **Auditar y** haga clic en **Siguiente**.

   :::image type="content" source="images/a8b934dab2dbba289cf64fe30e0e8aa4.png" alt-text="El Microsoft Endpoint Configuration Manager-4" lightbox="images/a8b934dab2dbba289cf64fe30e0e8aa4.png":::

4. Para confirmar la nueva directiva de protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="El Microsoft Endpoint Configuration Manager-5" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. Una vez creada la directiva, haga clic en **Cerrar**.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="El Microsoft Endpoint Configuration Manager-6" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="El Microsoft Endpoint Configuration Manager-7" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::


7. Dirigir la directiva a la colección recién Windows y haga clic en **Aceptar**.


:::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="El Microsoft Endpoint Configuration Manager-8" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Ahora ha configurado correctamente Acceso controlado a carpetas en modo auditoría.

## <a name="related-topic"></a>Tema relacionado

- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
