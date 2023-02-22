---
title: Configurar la implementación de Microsoft Defender para punto de conexión
description: Aprenda a configurar la implementación para Microsoft Defender para punto de conexión
keywords: deploy, setup, licensing validation, tenant configuration, network configuration
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
- m365-security
- m365solution-endpointprotect
- m365solution-scenario
- highpri
- tier1
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 5369f6a359602166b3b2302bd268a7fa4e8b3c4e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637670"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Configurar la implementación de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La implementación de Defender para punto de conexión es un proceso de tres fases:

|[![fase de implementación: preparación.](images/phase-diagrams/prepare.png#lightbox)](prepare-deployment.md)<br>[Fase 1: Preparación](prepare-deployment.md) | ![fase de implementación: configuración](images/phase-diagrams/setup.png#lightbox)<br>Fase 2: Configuración | [![fase de implementación: incorporación](images/phase-diagrams/onboard.png#lightbox)](onboarding.md)<br>[Fase 3: Incorporación](onboarding.md)|
|---|---|---|
||*¡Estás aquí!*||

Actualmente se encuentra en la fase de configuración.

En este escenario de implementación, se le guiará por los pasos siguientes:

- Validación de licencias
- Configuración del tenant
- Configuración de red

> [!NOTE]
> Con el fin de guiarle a través de una implementación típica, este escenario solo cubrirá el uso de Microsoft Endpoint Configuration Manager. Defender para punto de conexión admite el uso de otras herramientas de incorporación, pero no cubrirá esos escenarios en la guía de implementación. Para obtener más información, consulte [Incorporación de dispositivos a Microsoft Defender para punto de conexión](onboard-configure.md).

## <a name="check-license-state"></a>Comprobación del estado de la licencia

La comprobación del estado de la licencia y si se aprovisionó correctamente se puede realizar a través del Centro de administración o a través de **Microsoft Azure Portal**.

1. Para ver las licencias, vaya a **Microsoft Azure Portal** y vaya a la [sección Licencia de Microsoft Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).

   :::image type="content" source="images/atp-licensing-azure-portal.png" alt-text="Página Licencias de Azure" lightbox="images/atp-licensing-azure-portal.png":::

2. Como alternativa, en el centro de administración, vaya a **Facturación \> Suscripciones**.

    En la pantalla, verá todas las licencias aprovisionadas y su **estado** actual.

    :::image type="content" source="images/atp-billing-subscriptions.png" alt-text="Página de licencias de facturación" lightbox="images/atp-billing-subscriptions.png":::

## <a name="cloud-service-provider-validation"></a>Validación del proveedor de servicios en la nube

Para obtener acceso a las licencias que se aprovisionan en su empresa y comprobar el estado de las licencias, vaya al centro de administración.

1. En el **portal de partners**, seleccione **Administrar servicios > Office 365**.

2. Al hacer clic en el vínculo **Portal de partners**, se abrirá la opción **Administración en nombre** y se le dará acceso al centro de administración del cliente.

   :::image type="content" source="images/atp-O365-admin-portal-customer.png" alt-text="El portal de administración de Office 365" lightbox="images/atp-O365-admin-portal-customer.png":::

## <a name="tenant-configuration"></a>Configuración del tenant

La incorporación a Microsoft Defender para punto de conexión es fácil. En el menú de navegación, seleccione cualquier elemento de la sección Puntos de conexión o cualquier característica de Microsoft 365 Defender, como Incidentes, Búsqueda, Centro de acciones o Análisis de amenazas para iniciar el proceso de incorporación.

Desde un explorador web, vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

## <a name="data-center-location"></a>Ubicación del centro de datos
Microsoft Defender para punto de conexión almacenará y procesará los datos en la [misma ubicación que usa Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable). Si aún no se ha activado Microsoft 365 Defender, la incorporación a Microsoft Defender para punto de conexión también activará Microsoft 365 Defender y se seleccionará automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos. La ubicación del centro de datos seleccionada se muestra en la pantalla.

## <a name="network-configuration"></a>Configuración de red

Si la organización no requiere que los puntos de conexión usen un proxy para acceder a Internet, omita esta sección.

El sensor de Microsoft Defender para punto de conexión requiere los servicios HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión. El sensor de Microsoft Defender para punto de conexión incrustado se ejecuta en el contexto del sistema mediante la cuenta LocalSystem. El sensor usa los servicios HTTP de Microsoft Windows (WinHTTP) para habilitar la comunicación con el servicio en la nube de Microsoft Defender para punto de conexión. La configuración de WinHTTP es independiente de la configuración del proxy de exploración de Internet de Windows Internet (WinINet) y solo puede detectar un servidor proxy mediante los siguientes métodos de detección:

- **Métodos de detección automática**:
  - Proxy transparente
  - Protocolo de detección automática de proxy web (WPAD)

  Si se ha implementado un proxy transparente o WPAD en la topología de red, no es necesario realizar valores de configuración especiales. Para obtener más información sobre las exclusiones de direcciones URL de Microsoft Defender para punto de conexión en el proxy, consulte la sección [Direcciones URL del servicio proxy](production-deployment.md#proxy-service-urls) de este documento para ver la lista de direcciones URL permitidas o la [Configuración de las opciones de proxy de dispositivo y de conectividad a Internet](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

- **Configuración de proxy estático manual**:
  - Configuración basada en el registro
  - Configuración de WinHTTP mediante el comando netsh

    Solo es adecuado para escritorios en una topología estable (por ejemplo, un escritorio en una red corporativa detrás del mismo proxy).

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configuración manual del servidor proxy mediante un proxy estático basado en el registro

Configure un proxy estático basado en el Registro para permitir que solo el sensor de Microsoft Defender para punto de conexión informe de datos de diagnóstico y se comunique con los servicios de Microsoft Defender para punto de conexión si un equipo no tiene permiso para conectarse a Internet. El proxy estático se puede configurar mediante la directiva de grupo (GP). La directiva de grupo se puede encontrar aquí:

- Plantillas administrativas \> Componentes de Windows \> Recopilación de datos y compilaciones en versión preliminar \> Configurar el uso del proxy autenticado para el servicio de telemetría y experiencia del usuario conectado
- Establézcalo en **Habilitado** y seleccione **Deshabilitar el uso del proxy autenticado**.

1. Abra la Consola de administración de directivas de grupo.
2. Cree una directiva o edite una directiva existente basada en las prácticas de la organización.
3. Edite la directiva de grupo y vaya a **Plantillas administrativas \> Componentes de Windows \> Recopilación de datos y compilaciones en versión preliminar \> Configurar el uso del proxy autenticado para el servicio de telemetría y experiencia del usuario conectado**.

   :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="Opciones relacionadas con la configuración de la directiva de uso" lightbox="images/atp-gpo-proxy1.png":::

4. Seleccione **Habilitado**.
5. Seleccione **Deshabilitar el uso del proxy autenticado**.
6. Vaya a **Plantillas administrativas \> Componentes de Windows \> Recopilación de datos y compilaciones en versión preliminar \> Configurar experiencias de usuario conectadas y telemetría**.

   :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="Las opciones relacionadas con la configuración de la experiencia del usuario conectado y la telemetría" lightbox="images/atp-gpo-proxy2.png":::

7. Seleccione **Habilitado**.
8. Escriba el **nombre del servidor proxy**.

La directiva establece dos valores del registro `TelemetryProxyServer` como REG_SZ y `DisableEnterpriseAuthProxy` como REG_DWORD en la clave del registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.

El valor `TelemetryProxyServer` del Registro tiene el siguiente formato de cadena:

```text
<server name or ip>:<port>
```

Por ejemplo, 10.0.0.6:8080

El valor del registro `DisableEnterpriseAuthProxy` debe establecerse en 1.

### <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configuración manual del servidor proxy mediante el comando netsh

Use netsh para configurar un proxy estático en todo el sistema.

> [!NOTE]
>
> - Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.
> - Los equipos portátiles que están cambiando la topología (por ejemplo: de oficina a casa) no funcionarán correctamente con netsh. Use la configuración de proxy estático basada en el registro.

1. Abra un símbolo del sistema con privilegios elevados:
    1. Vaya a **Inicio** y escriba **cmd**.
    1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Por ejemplo: netsh winhttp set proxy 10.0.0.6:8080

### <a name="proxy-configuration-for-down-level-devices"></a>Configuración de proxy para dispositivos de nivel inferior

Los dispositivos de nivel inferior incluyen estaciones de trabajo de Windows 7 SP1 y Windows 8.1, así como Windows Server 2008 R2 y otros sistemas operativos de servidor que se han incorporado anteriormente mediante Microsoft Monitoring Agent. Estos sistemas operativos tendrán el proxy configurado como parte del Agente de administración de Microsoft para controlar la comunicación desde el punto de conexión a Azure. Consulte la Guía de implementación rápida del Agente de administración de Microsoft para obtener información sobre cómo se configura un proxy en estos dispositivos.

### <a name="proxy-service-urls"></a>Direcciones URL del servicio proxy

Las direcciones URL que incluyen v20 solo son necesarias si tiene dispositivos Windows 10, versión 1803 o Windows 11. Por ejemplo, `us-v20.events.data.microsoft.com` solo es necesario si el dispositivo está en Windows 10, versión 1803 o Windows 11.

Si un proxy o firewall bloquea el tráfico anónimo, como el sensor de Microsoft Defender para punto de conexión se conecta desde el contexto del sistema, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Asegúrese de que no hay reglas de filtrado de red o de firewall que denieguen el acceso a estas direcciones URL, o puede que tenga que crear una regla *de permiso* específicamente para ellas.

<br>

****


|Hoja de cálculo de la lista de dominios| Descripción|
|---|---|
|Lista de direcciones URL de Microsoft Defender para punto de conexión para clientes comerciales| Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes comerciales. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
|Lista de direcciones URL de Microsoft Defender para punto de conexión para Gov/GCC/DoD | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes de Gov/GCC/DoD. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

## <a name="next-step"></a>Paso siguiente

[![**Fase 3: Incorporación**.](images/onboard.png#lightbox)] <br> [Fase 3: Incorporación](onboarding.md): Incorporación de dispositivos al servicio para que el servicio de Microsoft Defender para punto de conexión pueda obtener datos del sensor de ellos.
