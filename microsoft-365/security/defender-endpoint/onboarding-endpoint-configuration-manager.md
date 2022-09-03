---
title: Incorporación mediante Microsoft Endpoint Configuration Manager
description: Obtenga información sobre cómo incorporarse a Microsoft Defender para punto de conexión mediante Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, Microsoft Defender para punto de conexión, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint configuration manager
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 37dd9e55422520fbd2fe1cce88d052503a331b9b
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67575831"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Incorporación mediante Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este artículo forma parte de la guía de implementación y actúa como un método de incorporación de ejemplo.

En el tema [Planeamiento](deployment-strategy.md) , se proporcionaron varios métodos para incorporar dispositivos al servicio. En este tema se trata la arquitectura de administración conjunta.

:::image type="content" source="images/co-management-architecture.png" alt-text="Arquitectura nativa de la nube" lightbox="images/co-management-architecture.png":::
*Diagrama de arquitecturas de entorno*

Aunque Defender para punto de conexión admite la incorporación de varios puntos de conexión y herramientas, en este artículo no se tratan. Para obtener información sobre la incorporación general mediante otras herramientas y métodos de implementación admitidos, consulte [Introducción a la incorporación](onboarding.md).

Este tema guía a los usuarios en:

- Paso 1: Incorporación de dispositivos Windows al servicio
- Paso 2: Configuración de las funcionalidades de Defender para punto de conexión

Esta guía de incorporación le guiará por los siguientes pasos básicos que debe seguir al usar Microsoft Endpoint Configuration Manager:

- **Creación de una colección en Microsoft Endpoint Configuration Manager**
- **Configuración de funcionalidades de Microsoft Defender para punto de conexión mediante Microsoft Endpoint Configuration Manager**

> [!NOTE]
> En esta implementación de ejemplo solo se tratan los dispositivos Windows.

## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Paso 1: Incorporación de dispositivos Windows mediante Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Creación de colecciones

Para incorporar dispositivos Windows con el punto de conexión de Microsoft Configuration Manager, la implementación puede tener como destino una colección existente o se puede crear una nueva colección para realizar pruebas.

La incorporación mediante herramientas como la directiva de grupo o el método manual no instala ningún agente en el sistema.

Dentro del punto de conexión de Microsoft Configuration Manager consola, el proceso de incorporación se configurará como parte de la configuración de cumplimiento dentro de la consola.

Cualquier sistema que reciba esta configuración necesaria mantendrá esa configuración mientras el cliente Configuration Manager siga recibiendo esta directiva desde el punto de administración.

Siga los pasos siguientes para incorporar puntos de conexión mediante microsoft endpoint Configuration Manager.

1. En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Device Collections (Recopilaciones de dispositivos de información general sobre \> recursos y cumplimiento\>**).

    :::image type="content" source="images/configmgr-device-collections.png" alt-text="Asistente de Configuration Manager de punto de conexión de Microsoft1" lightbox="images/configmgr-device-collections.png":::

2. Haga clic con el botón derecho en **Recopilación de dispositivos** y seleccione **Crear recopilación de dispositivos**.

    :::image type="content" source="images/configmgr-create-device-collection.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft2" lightbox="images/configmgr-create-device-collection.png":::

3. Proporcione un **nombre** y **una colección de límites** y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="images/configmgr-limiting-collection.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft3" lightbox="images/configmgr-limiting-collection.png":::

4. Seleccione **Agregar regla** y elija **Regla de consulta**.

    :::image type="content" source="images/configmgr-query-rule.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft4" lightbox="images/configmgr-query-rule.png":::

5. Haga clic en **Siguiente** en el **Asistente para pertenencia directa** y haga clic en **Editar instrucción de consulta**.

    :::image type="content" source="images/configmgr-direct-membership.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft5" lightbox="images/configmgr-direct-membership.png":::

6. Seleccione **Criterios** y, a continuación, elija el icono de estrella.

    :::image type="content" source="images/configmgr-criteria.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft6" lightbox="images/configmgr-criteria.png":::

7. Mantenga el tipo de criterio como **valor simple**, elija dónde como **Sistema operativo: número de compilación**, operador como **mayor o igual que** y valor **14393** y haga clic en **Aceptar**.

    :::image type="content" source="images/configmgr-simple-value.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft7" lightbox="images/configmgr-simple-value.png":::

8. Seleccione **Siguiente** y **Cerrar**.

    :::image type="content" source="images/configmgr-membership-rules.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft8" lightbox="images/configmgr-membership-rules.png":::

9. Seleccione **Siguiente**.

    :::image type="content" source="images/configmgr-confirm.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft9" lightbox="images/configmgr-confirm.png":::

Después de completar esta tarea, ahora tiene una recopilación de dispositivos con todos los puntos de conexión de Windows en el entorno.

## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Paso 2: Configurar funcionalidades de Microsoft Defender para punto de conexión

Esta sección le guía en la configuración de las siguientes funcionalidades mediante microsoft endpoint Configuration Manager en dispositivos Windows:

- [**Detección y respuesta de puntos de conexión**](#endpoint-detection-and-response)
- [**Protección de última generación**](#next-generation-protection)
- [**Reducción de la superficie expuesta a ataques**](#attack-surface-reduction)

### <a name="endpoint-detection-and-response"></a>Detección y respuesta de puntos de conexión

#### <a name="windows-10-and-windows-11"></a>Windows 10 y Windows 11

Desde el portal de Microsoft 365 Defender es posible descargar la `.onboarding` directiva que se puede usar para crear la directiva en System Center Configuration Manager e implementarla en dispositivos Windows 10 y Windows 11.

1. En un <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, seleccione [Configuración y, a continuación, Incorporación](https://security.microsoft.com/preferences2/onboarding).

2. En Método de implementación, seleccione la versión compatible de **Microsoft Endpoint Configuration Manager**.

    :::image type="content" source="images/mdatp-onboarding-wizard.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft10" lightbox="images/mdatp-onboarding-wizard.png":::

3. Seleccione **Descargar paquete**.

   :::image type="content" source="images/mdatp-download-package.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft11" lightbox="images/mdatp-download-package.png":::

4. Guarde el paquete en una ubicación accesible.
5. En Microsoft Endpoint Configuration Manager, vaya a: **Recursos y compatibilidad > Información general > Endpoint Protection > Directivas de ATP de Microsoft Defender**.

6. Haga clic con el botón derecho en **Directivas de ATP de Microsoft Defender** y seleccione **Crear directiva de ATP de Microsoft Defender**.

    :::image type="content" source="images/configmgr-create-policy.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft12" lightbox="images/configmgr-create-policy.png":::

7. Escriba el nombre y la descripción, compruebe **que La incorporación** está seleccionada y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="images/configmgr-policy-name.png" alt-text="Asistente para Configuration Manager de punto de conexión de Microsoft13" lightbox="images/configmgr-policy-name.png":::

8. Haga clic en **Examinar**.

9. Vaya a la ubicación del archivo descargado del paso 4 anterior.

10. Haga clic en **Siguiente**.
11. Configure el agente con los ejemplos adecuados (**Ninguno** o **Todos los tipos de archivo**).

    :::image type="content" source="images/configmgr-config-settings.png" alt-text="Los valores de configuración1" lightbox="images/configmgr-config-settings.png":::

12. Seleccione la telemetría adecuada (**Normal** o **Acelerada**) y haga clic en **Siguiente**.

    :::image type="content" source="images/configmgr-telemetry.png" alt-text="Los valores de configuración2" lightbox="images/configmgr-telemetry.png":::

13. Compruebe la configuración y haga clic en **Siguiente**.

    :::image type="content" source="images/configmgr-verify-configuration.png" alt-text="La configuración de configuración3" lightbox="images/configmgr-verify-configuration.png":::

14. Haga clic en **Cerrar** cuando se complete el asistente.

15. En la consola de Microsoft Endpoint Configuration Manager, haga clic con el botón derecho en la directiva de Defender para punto de conexión que acaba de crear y seleccione **Implementar**.

    :::image type="content" source="images/configmgr-deploy.png" alt-text="Los valores de configuración4" lightbox="images/configmgr-deploy.png":::

16. En el panel derecho, seleccione la colección creada anteriormente y haga clic en **Aceptar**.

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="La configuración5" lightbox="images/configmgr-select-collection.png":::

#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Versiones anteriores del cliente de Windows (Windows 7 y Windows 8.1)

Siga los pasos siguientes para identificar el identificador del área de trabajo de Defender para punto de conexión y la clave del área de trabajo, que serán necesarios para la incorporación de versiones anteriores de Windows.

1. En un <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, seleccione **Configuración** \> **Puntos de conexión** \> **Incorporación** (en **Administración de dispositivos**).

2. En sistema operativo, elija **Windows 7 SP1 y 8.1**.

3. Copie el **identificador del área de trabajo** y la **clave del área de trabajo** y guárdelos. Se usarán más adelante en el proceso.

   :::image type="content" source="images/91b738e4b97c4272fd6d438d8c2d5269.png" alt-text="Proceso de incorporación" lightbox="images/91b738e4b97c4272fd6d438d8c2d5269.png":::

4. Instale Microsoft Monitoring Agent (MMA).

   MMA es actualmente (a partir de enero de 2019) compatible con los siguientes sistemas operativos Windows:

   - SKU de servidor: Windows Server 2008 SP1 o posterior
   - SKU de cliente: Windows 7 SP1 y versiones posteriores

   El agente MMA tendrá que instalarse en dispositivos Windows. Para instalar el agente, algunos sistemas deberán descargar la [actualización para la experiencia del cliente y la telemetría de diagnóstico](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) con el fin de recopilar los datos con MMA. Estas versiones del sistema incluyen, entre otras, las siguientes:

   - Windows 8.1
   - Windows 7
   - Windows Server 2016
   - Windows Server 2012 R2
   - Windows Server 2008 R2

   En concreto, para Windows 7 SP1, se deben instalar las siguientes revisiones:

   - Instalar [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
   - Instale [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) **o** [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework). No instale ambos en el mismo sistema.

5. Si usa un proxy para conectarse a Internet, consulte la sección Configuración de proxy.

Una vez completado, debería ver los puntos de conexión incorporados en el portal en un plazo de una hora.

### <a name="next-generation-protection"></a>Protección de última generación

El Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona una protección de última generación para equipos de escritorio, equipos portátiles y servidores.

1. En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Antimalware Polices (Directivas antimalware de Endpoint Protection \> de Información general \> sobre activos y cumplimiento\>**) y elija **Create Antimalware Policy (Crear directiva antimalware**).

   :::image type="content" source="images/9736e0358e86bc778ce1bd4c516adb8b.png" alt-text="Directiva antimalware" lightbox="images/9736e0358e86bc778ce1bd4c516adb8b.png":::

2. Seleccione **Exámenes programados**, **Configuración de examen**, **Acciones predeterminadas**, **Protección en tiempo real**, **Configuración de exclusión**, **Opciones avanzadas**, **Invalidaciones de amenazas**, **Servicio de protección** en la nube y **Actualizaciones de inteligencia de seguridad** y elija **Aceptar**.

   :::image type="content" source="images/1566ad81bae3d714cc9e0d47575a8cbd.png" alt-text="Panel de protección de próxima generación1" lightbox="images/1566ad81bae3d714cc9e0d47575a8cbd.png":::

    En determinados sectores o algunos clientes empresariales selectos pueden tener necesidades específicas sobre cómo se configura Antivirus.

    [Examen rápido frente a examen completo y examen personalizado](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Para obtener más información, consulte [Seguridad de Windows marco de configuración](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework).
  
    :::image type="content" source="images/cd7daeb392ad5a36f2d3a15d650f1e96.png" alt-text="Panel de protección de próxima generación2" lightbox="images/cd7daeb392ad5a36f2d3a15d650f1e96.png":::

    :::image type="content" source="images/36c7c2ed737f2f4b54918a4f20791d4b.png" alt-text="Panel de protección de última generación3" lightbox="images/36c7c2ed737f2f4b54918a4f20791d4b.png":::

    :::image type="content" source="images/a28afc02c1940d5220b233640364970c.png" alt-text="Panel de protección de última generación4" lightbox="images/a28afc02c1940d5220b233640364970c.png":::

    :::image type="content" source="images/5420a8790c550f39f189830775a6d4c9.png" alt-text="Panel de protección de última generación5" lightbox="images/5420a8790c550f39f189830775a6d4c9.png":::

    :::image type="content" source="images/33f08a38f2f4dd12a364f8eac95e8c6b.png" alt-text="Panel de protección de última generación6" lightbox="images/33f08a38f2f4dd12a364f8eac95e8c6b.png":::

    :::image type="content" source="images/41b9a023bc96364062c2041a8f5c344e.png" alt-text="Panel de protección de última generación7" lightbox="images/41b9a023bc96364062c2041a8f5c344e.png":::

    :::image type="content" source="images/945c9c5d66797037c3caeaa5c19f135c.png" alt-text="Panel de protección de última generación8" lightbox="images/945c9c5d66797037c3caeaa5c19f135c.png":::

    :::image type="content" source="images/3876ca687391bfc0ce215d221c683970.png" alt-text="Panel de protección de próxima generación9" lightbox="images/3876ca687391bfc0ce215d221c683970.png":::

3. Haga clic con el botón derecho en la directiva antimalware recién creada y seleccione **Implementar**.

    :::image type="content" source="images/f5508317cd8c7870627cb4726acd5f3d.png" alt-text="Panel de protección de última generación10" lightbox="images/f5508317cd8c7870627cb4726acd5f3d.png":::

4. Dirija la nueva directiva antimalware a la colección de Windows y haga clic en **Aceptar**.

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="Panel de protección de próxima generación11" lightbox="images/configmgr-select-collection.png":::

Después de completar esta tarea, ahora ha configurado correctamente el Antivirus de Microsoft Defender.

### <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

El pilar de reducción de la superficie expuesta a ataques de Defender para punto de conexión incluye el conjunto de características que está disponible en Protección contra vulnerabilidades de seguridad. Reglas de reducción de la superficie expuesta a ataques (ASR), acceso controlado a carpetas, protección de red y protección contra vulnerabilidades de seguridad.

Todas estas características proporcionan un modo de auditoría y un modo de bloque. En el modo de auditoría no hay ningún impacto en el usuario final. Todo lo que hace es recopilar telemetría adicional y hacer que esté disponible en el portal de Microsoft 365 Defender. El objetivo de una implementación es mover paso a paso los controles de seguridad al modo de bloque.

Para establecer reglas de ASR en modo auditoría:

1. En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** y elija Crear directiva de **Protección contra vulnerabilidades** de seguridad.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="El punto de conexión de Microsoft Configuration Manager consola0" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. Seleccione **Reducción de superficie expuesta a ataques**.

3. Establezca reglas en **Auditar** y haga clic en **Siguiente**.

   :::image type="content" source="images/d18e40c9e60aecf1f9a93065cb7567bd.png" alt-text="El punto de conexión de Microsoft Configuration Manager console1" lightbox="images/d18e40c9e60aecf1f9a93065cb7567bd.png":::

4. Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="Microsoft Endpoint Configuration Manager console2" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. Una vez creada la directiva, haga clic en **Cerrar**.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="El punto de conexión de Microsoft Configuration Manager consola3" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Haga clic con el botón derecho en la directiva recién creada y elija **Implementar**.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="El punto de conexión de Microsoft Configuration Manager consola4" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. Dirija la directiva a la colección de Windows recién creada y haga clic en **Aceptar**.

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="El punto de conexión de Microsoft Configuration Manager consola5" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Después de completar esta tarea, ahora ha configurado correctamente las reglas de ASR en modo de auditoría.

A continuación se muestran pasos adicionales para comprobar si las reglas de ASR se aplican correctamente a los puntos de conexión. (Esto puede tardar unos minutos)

1. Desde un explorador web, vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>.

2. Seleccione **Administración de configuración** en el menú de la izquierda.

3. Haga clic en **Ir a la administración de superficies expuestas a ataques** en el panel Administración de superficie expuesta a ataques.

   :::image type="content" source="images/security-center-attack-surface-mgnt-tile.png" alt-text="Administración de la superficie expuesta a ataques" lightbox="images/security-center-attack-surface-mgnt-tile.png":::

4. Haga clic en la pestaña **Configuración** en Informes de reglas de reducción de superficie expuesta a ataques. Muestra información general sobre la configuración de reglas de ASR y el estado de las reglas de ASR en cada dispositivo.

   :::image type="content" source="images/f91f406e6e0aae197a947d3b0e8b2d0d.png" alt-text="Las reglas de reducción de superficie expuesta a ataques informan1" lightbox="images/f91f406e6e0aae197a947d3b0e8b2d0d.png":::

5. Haga clic en cada dispositivo para ver los detalles de configuración de las reglas de ASR.

   :::image type="content" source="images/24bfb16ed561cbb468bd8ce51130ca9d.png" alt-text="Las reglas de reducción de superficie expuesta a ataques informan2" lightbox="images/24bfb16ed561cbb468bd8ce51130ca9d.png":::

Consulte [Optimización de la implementación y detecciones de reglas de ASR](/microsoft-365/security/defender-endpoint/configure-machines-asr) para obtener más detalles.

#### <a name="set-network-protection-rules-in-audit-mode"></a>Establecimiento de reglas de protección de red en modo auditoría

1. En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** y elija Crear directiva de **Protección contra vulnerabilidades** de seguridad.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="The System Center Configuration Manager1" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. Seleccione **Protección de red**.

3. Establezca la configuración en **Auditar** y haga clic en **Siguiente**.

   :::image type="content" source="images/c039b2e05dba1ade6fb4512456380c9f.png" alt-text="The System Center Configuration Manager2" lightbox="images/c039b2e05dba1ade6fb4512456380c9f.png":::

4. Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="La directiva de Protección contra vulnerabilidades1" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. Una vez creada la directiva, haga clic en **Cerrar**.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="La directiva de Protección contra vulnerabilidades2" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Haga clic con el botón derecho en la directiva recién creada y elija **Implementar**.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="El punto de conexión de Microsoft Configuration Manager-1" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. Seleccione la directiva en la colección de Windows recién creada y elija **Aceptar**.

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="El punto de conexión de Microsoft Configuration Manager-2" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Después de completar esta tarea, ahora ha configurado correctamente Protección de red en modo de auditoría.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Para establecer reglas de acceso controlado a carpetas en modo auditoría

1. En la consola de Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance** > **Overview** > **Endpoint Protection** >  **Windows Defender Exploit Guard** y, a continuación, elija **Crear directiva de Protección contra vulnerabilidades de seguridad**.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="El punto de conexión de Microsoft Configuration Manager-3" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. Seleccione **Acceso controlado a carpetas**.

3. Establezca la configuración en **Auditar** y haga clic en **Siguiente**.

   :::image type="content" source="images/a8b934dab2dbba289cf64fe30e0e8aa4.png" alt-text="El punto de conexión de Microsoft Configuration Manager-4" lightbox="images/a8b934dab2dbba289cf64fe30e0e8aa4.png":::

4. Confirme la nueva directiva de Protección contra vulnerabilidades haciendo clic en **Siguiente**.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="El punto de conexión de Microsoft Configuration Manager-5" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. Una vez creada la directiva, haga clic en **Cerrar**.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="El punto de conexión de Microsoft Configuration Manager-6" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Haga clic con el botón derecho en la directiva recién creada y elija **Implementar**.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="El punto de conexión de Microsoft Configuration Manager-7" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::


7. Dirija la directiva a la colección de Windows recién creada y haga clic en **Aceptar**.


:::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="El punto de conexión de Microsoft Configuration Manager-8" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Ahora ha configurado correctamente el acceso controlado a carpetas en modo de auditoría.

## <a name="related-topic"></a>Tema relacionado

- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
