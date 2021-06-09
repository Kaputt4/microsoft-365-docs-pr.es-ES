---
title: Incorporación mediante Microsoft Endpoint Configuration Manager
description: Obtenga información sobre cómo incorporarse a Microsoft Defender para endpoint mediante Microsoft Endpoint Configuration Manager
keywords: incorporación, configuración, implementación, administrador de configuración de puntos de conexión, Microsoft Defender para endpoint, creación de colecciones, respuesta de detección de puntos de conexión, protección de próxima generación, reducción de superficie de ataque, administrador de configuración de puntos de conexión de Microsoft
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
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843511"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Incorporación mediante Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Este artículo forma parte de la guía de implementación y actúa como un método de incorporación de ejemplo. 

En el [tema Planeación,](deployment-strategy.md) se proporcionaron varios métodos para incorporar dispositivos al servicio. En este tema se trata la arquitectura de administración en colaboración. 

![Imagen de arquitectura nativa de la nube ](images/co-management-architecture.png)
 *Diagrama de arquitecturas de entorno*


Aunque Defender para endpoint admite la incorporación de varios puntos de conexión y herramientas, este artículo no los cubre. Para obtener información sobre la incorporación general con otras herramientas y métodos de implementación compatibles, vea [Onboarding overview](onboarding.md).



En este tema se guía a los usuarios en:
- Paso 1: Incorporación de Windows dispositivos al servicio 
- Paso 2: Configuración de las capacidades de Defender para puntos de conexión

Esta guía de incorporación le ayudará a seguir los siguientes pasos básicos que debe seguir al usar Microsoft Endpoint Configuration Manager:
- **Crear una colección en Microsoft Endpoint Configuration Manager**
- **Configurar Las capacidades de Microsoft Defender para puntos de conexión mediante Microsoft Endpoint Configuration Manager**

>[!NOTE]
>Solo Windows dispositivos se tratan en este ejemplo de implementación. 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Paso 1: Incorporación Windows dispositivos con Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Creación de colecciones
Para incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager, la implementación puede dirigirse a una colección existente o se puede crear una nueva colección para pruebas. 

La incorporación mediante herramientas como la directiva de grupo o el método manual no instala ningún agente en el sistema. 

Dentro de Microsoft Endpoint Configuration Manager consola, el proceso de incorporación se configurará como parte de la configuración de cumplimiento dentro de la consola.

Cualquier sistema que reciba esta configuración necesaria mantendrá esa configuración mientras el cliente de Configuration Manager siga recibiendo esta directiva desde el punto de administración. 

Siga los pasos siguientes para incorporar puntos de conexión mediante Microsoft Endpoint Configuration Manager.

1. En Microsoft Endpoint Configuration Manager consola, vaya a **Assets and Compliance Overview Device \> \> Collections**.            

    ![Imagen de Microsoft Endpoint Configuration Manager wizard1](images/configmgr-device-collections.png)

2. Haga clic con el **botón secundario en Colección de** dispositivos y seleccione Crear colección de **dispositivos**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard2](images/configmgr-create-device-collection.png)

3. Proporcione una **colección Name** y **Limiting y,** a continuación, **seleccione Siguiente**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard3](images/configmgr-limiting-collection.png)

4. Seleccione **Agregar regla** y elija Regla de **consulta**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard4](images/configmgr-query-rule.png)

5.  Haga **clic en Siguiente** en el Asistente para pertenencia **directa** y haga clic en Editar **instrucción query**.

     ![Imagen de Microsoft Endpoint Configuration Manager wizard5](images/configmgr-direct-membership.png)

6. Seleccione **Criterios** y, a continuación, elija el icono de estrella.

     ![Imagen de Microsoft Endpoint Configuration Manager wizard6](images/configmgr-criteria.png)

7. Mantenga el tipo de criterio como valor **simple**,  elija dónde como Sistema operativo **-** número de compilación , operador como mayor o igual que y valor **14393** y haga clic en **Aceptar**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard7](images/configmgr-simple-value.png)

8. Seleccione **Siguiente** y **Cerrar**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard8](images/configmgr-membership-rules.png)

9. Seleccione **Siguiente**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard9](images/configmgr-confirm.png)


Después de completar esta tarea, ahora tienes una colección de dispositivos con todos los Windows 10 en el entorno. 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Paso 2: Configurar Microsoft Defender para las funcionalidades de punto de conexión 
En esta sección se le guía en la configuración de las siguientes funcionalidades mediante Microsoft Endpoint Configuration Manager en Windows dispositivos:

- [**EDR**](#endpoint-detection-and-response)
- [**Protección de última generación**](#next-generation-protection)
- [**Reducción de la superficie expuesta a ataques**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>EDR
#### <a name="windows-10"></a>Windows 10
Desde dentro del Centro de seguridad de Microsoft Defender es posible descargar la directiva ".onboarding" que se puede usar para crear la directiva en System Center Configuration Manager e implementar esa directiva en Windows 10 dispositivos.

1. En un portal Centro de seguridad de Microsoft Defender, [seleccione Configuración y,](https://securitycenter.windows.com/preferences2/onboarding)a continuación, Incorporación .



2. En Método de implementación, seleccione la versión compatible **de Microsoft Endpoint Configuration Manager**.

    ![Imagen del Asistente para incorporación de Microsoft Defender para endpoint10](images/mdatp-onboarding-wizard.png)

3. Seleccione **Descargar paquete**.

    ![Imagen del Asistente para la incorporación de Microsoft Defender para puntos de conexión11](images/mdatp-download-package.png)

4. Guarde el paquete en una ubicación accesible.
5. En Microsoft Endpoint Configuration Manager, vaya a: **Assets and Compliance > Overview > Endpoint Protection > ATP de Microsoft Defender Policies**.

6. Haga clic con el **botón ATP de Microsoft Defender y** seleccione Crear ATP de Microsoft Defender **directiva**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard12](images/configmgr-create-policy.png)

7. Escriba el nombre y la descripción, compruebe **que la incorporación** está seleccionada y, a continuación, seleccione **Siguiente**.

    ![Imagen de Microsoft Endpoint Configuration Manager wizard13](images/configmgr-policy-name.png)


8. Haga clic en **Examinar**.

9. Vaya a la ubicación del archivo descargado desde el paso 4 anterior.

10. Haga clic en **Siguiente**.
11. Configure el agente con los ejemplos adecuados (**Ninguno** o **Todos los tipos de archivo**).

    ![Imagen de las opciones de configuración1](images/configmgr-config-settings.png)

12. Seleccione la telemetría adecuada (**Normal** o **Expedited**) y, a continuación, haga clic **en Siguiente**.

    ![Imagen de las opciones de configuración2](images/configmgr-telemetry.png)

14. Compruebe la configuración y, a continuación, haga clic **en Siguiente**.

     ![Imagen de configuración3](images/configmgr-verify-configuration.png)

15. Haga **clic en** Cerrar cuando se complete el Asistente.

16.  En la Microsoft Endpoint Configuration Manager, haga clic con el botón secundario en la directiva defender para extremo que acaba de crear y seleccione **Implementar**.

     ![Imagen de las opciones de configuración4](images/configmgr-deploy.png)

17. En el panel derecho, seleccione la colección creada anteriormente y haga clic en **Aceptar**.

    ![Imagen de configuración5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Versiones anteriores de Windows Client (Windows 7 y Windows 8.1)
Siga los pasos que se indican a continuación para identificar el identificador del área de trabajo de endpoint y la clave de área de trabajo de Defender for Endpoint, que serán necesarios para la incorporación de versiones anteriores de Windows.

1. En un portal Centro de seguridad de Microsoft Defender, **seleccione Configuración > incorporación .**

2. En sistema operativo, **elija Windows 7 SP1 y 8.1**.

3. Copie el **identificador del área de trabajo** y la clave de área de **trabajo** y guárdelos. Se usarán más adelante en el proceso.

    ![Imagen de incorporación](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Instale el Microsoft Monitoring Agent (MMA). <br>
    MMA actualmente (a partir de enero de 2019) es compatible con los siguientes sistemas Windows operativos:

    -   SKU del servidor: Windows Server 2008 SP1 o versiones posteriores

    -   SKU de cliente: Windows 7 SP1 y versiones posteriores

    El agente mma tendrá que instalarse en Windows dispositivos. Para instalar el agente, algunos sistemas [](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) tendrán que descargar la actualización para la experiencia del cliente y la telemetría de diagnóstico para recopilar los datos con MMA. Estas versiones del sistema incluyen, pero no pueden limitarse a:

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    En concreto, para Windows 7 SP1, deben instalarse las siguientes revisiones:

    -   Instalar [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   Instale .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) **o** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).
        No instale ambos en el mismo sistema.

5. Si usa un proxy para conectarse a Internet, consulte la sección Configurar opciones de proxy.

Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.

### <a name="next-generation-protection"></a>Protección de última generación 
El Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona una protección de última generación para equipos de escritorio, equipos portátiles y servidores.

1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection \> \> \> Antimalware Polices** y elija **Create Antimalware Policy**.

    ![Imagen de la directiva antimalware](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. Seleccione **Exámenes programados,** Configuración del examen **,** Acciones predeterminadas **,** Protección en tiempo **real** **,** Configuración de exclusión **,** Avanzadas , Invalidaciones de **amenazas,** Servicio **de protección** en la nube y Actualizaciones de inteligencia de **seguridad** y elija **Aceptar**.

    ![Imagen del panel de protección de próxima generación1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    En determinados sectores o en algunos clientes empresariales selectos puede haber necesidades específicas sobre cómo se configura Antivirus.

  
    [Examen rápido frente a examen completo y examen personalizado](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Para obtener más información, [vea Seguridad de Windows marco de configuración](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![Imagen del panel de protección de próxima generación2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Imagen del panel de protección de próxima generación3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Imagen del panel de protección de próxima generación4](images/a28afc02c1940d5220b233640364970c.png)

    ![Imagen del panel de protección de próxima generación5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Imagen del panel de protección de próxima generación6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Imagen del panel de protección de próxima generación7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Imagen del panel de protección de próxima generación8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Imagen del panel de protección de próxima generación9](images/3876ca687391bfc0ce215d221c683970.png)

3. Haga clic con el botón secundario en la directiva antimalware recién creada y seleccione **Implementar**.

    ![Imagen del panel de protección de próxima generación10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. Dirigir la nueva directiva antimalware a la colección Windows 10 y haga clic en **Aceptar**.

     ![Imagen del panel de protección de próxima generación11](images/configmgr-select-collection.png)

Después de completar esta tarea, ahora ha configurado correctamente Antivirus de Windows Defender.

### <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques
El pilar de reducción de superficie de ataque de Defender para endpoint incluye el conjunto de características que está disponible en Protección contra vulnerabilidades de seguridad. Reglas de reducción de superficie de ataque (ASR), Acceso controlado a carpetas, Protección de red y Protección contra vulnerabilidades de seguridad. 

Todas estas características proporcionan un modo de auditoría y un modo de bloqueo. En el modo de auditoría no hay ningún impacto para el usuario final. Todo lo que hace es recopilar telemetría adicional y hacer que esté disponible en el Centro de seguridad de Microsoft Defender. El objetivo con una implementación es mover paso a paso los controles de seguridad al modo de bloqueo.

Para establecer reglas ASR en modo auditoría:

1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.

   ![Imagen de Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  Selecciona **Reducción de superficie de ataque**.
   

3. Establezca reglas en **Auditar** y haga clic **en Siguiente**.


    ![Imagen de Microsoft Endpoint Configuration Manager console1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.

    ![Imagen de Microsoft Endpoint Configuration Manager console2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. Una vez creada la directiva, haga clic **en Cerrar**.

    ![Imagen de Microsoft Endpoint Configuration Manager console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Imagen de Microsoft Endpoint Manager console1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.
    
    ![Imagen de Microsoft Endpoint Configuration Manager console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Dirigir la directiva a la colección recién Windows 10 y haga clic en **Aceptar**.

    ![Imagen de Microsoft Endpoint Configuration Manager console5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Después de completar esta tarea, ahora ha configurado correctamente las reglas de ASR en el modo de auditoría.  
  
A continuación se indican pasos adicionales para comprobar si las reglas ASR se aplican correctamente a los puntos de conexión. (Esto puede tardar unos minutos)


1. Desde un explorador web, vaya a <https://securitycenter.windows.com> .

2.  Seleccione **Administración de configuración** en el menú del lado izquierdo.

3. Haz **clic en Ir a la administración de superficies de** ataque en el panel Administración de superficie de ataque. 
    
    ![Imagen de la administración de superficies de ataque](images/security-center-attack-surface-mgnt-tile.png)

4. Haga clic **en la pestaña** Configuración en Informes de reglas de reducción de superficie de ataque. Muestra información general sobre la configuración de reglas ASR y el estado de las reglas ASR en cada dispositivo.

    ![Una captura de pantalla de informes de reglas de reducción de superficie de ataque1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. Haga clic en cada dispositivo para ver los detalles de configuración de las reglas de ASR.

    ![Una captura de pantalla de informes de reglas de reducción de superficie de ataque2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

Consulte [Optimizar la implementación y detecciones](/microsoft-365/security/defender-endpoint/configure-machines-asr)   de reglas ASR para obtener más información.  


#### <a name="set-network-protection-rules-in-audit-mode"></a>Establecer reglas de protección de red en modo auditoría:
1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.

    ![Una captura de System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Seleccione **Protección de red**.

3. Establezca la configuración en **Auditar** y haga clic en **Siguiente**. 

    ![Una captura System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. Para confirmar la nueva directiva de Protección contra vulnerabilidades de seguridad, haga clic en **Siguiente**.
    
    ![Una captura de pantalla Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Una vez creada la directiva, haga clic en **Cerrar**.

    ![Una captura de pantalla Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.

    ![Una captura de pantalla de Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Seleccione la directiva de la colección de Windows 10 recién creada y elija **Aceptar**.

    ![Una captura de pantalla de Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



Después de completar esta tarea, ahora ha configurado correctamente Protección de red en modo auditoría.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Para establecer reglas de acceso controlado a carpetas en modo auditoría:

1. En la Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** y elija **Create Exploit Guard Policy**.

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Seleccione **Acceso controlado a carpetas**.
    
3. Establezca la configuración en **Auditar** y haga clic **en Siguiente**.

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. Confirme la nueva directiva de Protección contra vulnerabilidades de seguridad haciendo clic en **Siguiente**.

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Una vez creada la directiva, haga clic en **Cerrar**.

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Haga clic con el botón secundario en la directiva recién creada y elija **Implementar**.

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  Dirigir la directiva a la colección recién Windows 10 y haga clic en **Aceptar**.

    ![Captura de pantalla de Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Ahora ha configurado correctamente Acceso controlado a carpetas en modo auditoría.

## <a name="related-topic"></a>Tema relacionado
- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
