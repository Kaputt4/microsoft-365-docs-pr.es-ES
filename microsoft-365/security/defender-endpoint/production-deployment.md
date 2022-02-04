---
title: Configurar Microsoft Defender para la implementación de puntos de conexión
description: Obtenga información sobre cómo configurar la implementación de Microsoft Defender para endpoint
keywords: 'implementación, configuración, validación de licencias, configuración de inquilino, configuración de red'
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
---

# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Configurar Microsoft Defender para la implementación de puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La implementación de Defender for Endpoint es un proceso de tres fases:

|[![fase de implementación: preparar.](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fase 1: Preparación](prepare-deployment.md) | ![fase de implementación: configuración](images/phase-diagrams/setup.png)<br>Fase 2: Configuración | [![fase de implementación: incorporación](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fase 3: Incorporación](onboarding.md)|
|---|---|---|
||*¡Estás aquí!*||

Actualmente se encuentra en la fase de configuración.

En este escenario de implementación, se le guiará a través de los pasos siguientes:

- Validación de licencias
- Configuración del espacio empresarial
- Configuración de red

> [!NOTE]
> Con el fin de guiarlo a través de una implementación típica, este escenario solo abarcará el uso de Microsoft Endpoint Configuration Manager. Defender for Endpoint admite el uso de otras herramientas de incorporación, pero no cubrirá esos escenarios en la guía de implementación. Para obtener más información, consulta [Incorporación de dispositivos a Microsoft Defender para endpoint](onboard-configure.md).

## <a name="check-license-state"></a>Comprobar el estado de la licencia

La comprobación del estado de la licencia y si se aprovisionó correctamente, se puede realizar a través del Centro de administración o a través **del portal Microsoft Azure usuario**.

1. Para ver las licencias, vaya al portal de Microsoft Azure **y** vaya a la [sección Microsoft Azure licencia del portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Imagen de la página Licencias de Azure.](images/atp-licensing-azure-portal.png)

1. Como alternativa, en el Centro de administración, vaya a **Suscripciones de** \> **facturación**.

    En la pantalla, verá todas las licencias aprovisionadas y su estado **actual**.

    ![Imagen de las licencias de facturación.](images/atp-billing-subscriptions.png)

## <a name="cloud-service-provider-validation"></a>Validación del proveedor de servicios en la nube

Para obtener acceso a las licencias que se aprovisionan a su empresa y comprobar el estado de las licencias, vaya al Centro de administración.

1. En el **portal de partners**, seleccione **Administrar servicios > Office 365**.

2. Al hacer clic en **el vínculo Portal** de partners, se abrirá la opción **Administrador** en nombre del usuario y se le dará acceso al Centro de administración de clientes.

   ![Imagen del portal de administración de O365.](images/atp-O365-admin-portal-customer.png)

## <a name="tenant-configuration"></a>Configuración del espacio empresarial

La incorporación a Microsoft Defender para Endpoint es fácil. En el menú de navegación, seleccione cualquier elemento en la sección Puntos de conexión o cualquier característica de Microsoft 365 Defender como Incidentes, Búsqueda, Centro de acción o Análisis de amenazas para iniciar el proceso de incorporación.

Desde un explorador web, vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender web</a>.

## <a name="data-center-location"></a>Ubicación del centro de datos
Microsoft Defender para endpoint almacenará y procesará datos en la [misma ubicación que usa Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable). Si Microsoft 365 Defender no se ha activado aún, la incorporación a Microsoft Defender para Endpoint también activará Microsoft 365 Defender y se seleccionará automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos. La ubicación del centro de datos seleccionada se muestra en la pantalla.

## <a name="network-configuration"></a>Configuración de red

Si la organización no requiere que los puntos de conexión usen un proxy para tener acceso a Internet, omita esta sección.

El sensor de Microsoft Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar los datos del sensor y comunicarse con el servicio Microsoft Defender para punto de conexión. El sensor incrustado de Microsoft Defender para endpoint se ejecuta en el contexto del sistema mediante la cuenta LocalSystem. El sensor usa los servicios HTTP de Microsoft Windows (WinHTTP) para habilitar la comunicación con el servicio en la nube Microsoft Defender para punto de conexión. La configuración de WinHTTP es independiente de la configuración de proxy de exploración de Internet de Windows (WinINet) y solo puede detectar un servidor proxy mediante los siguientes métodos de detección:

- **Métodos de detección automática**:
  - Proxy transparente
  - Protocolo de detección automática de proxy web (WPAD)

  Si se ha implementado un proxy transparente o WPAD en la topología de red, no es necesario que haya opciones de configuración especiales. Para obtener más información sobre las exclusiones de url de extremo de Microsoft Defender en el [](production-deployment.md#proxy-service-urls) proxy, vea la sección Direcciones URL del servicio proxy de este documento para la lista de direcciones URL permitidas o en Configurar el proxy de dispositivo y la configuración de [conectividad a Internet](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

- **Configuración manual de proxy estático**:
  - Configuración basada en el registro
  - WinHTTP configurado mediante el comando netsh

    Adecuado solo para escritorios en una topología estable (por ejemplo: un escritorio en una red corporativa detrás del mismo proxy).

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configurar manualmente el servidor proxy mediante un proxy estático basado en el registro

Configure un proxy estático basado en el Registro para permitir que solo el sensor de Microsoft Defender para endpoints informe datos de diagnóstico y se comunique con Microsoft Defender para los servicios de punto de conexión si un equipo no tiene permiso para conectarse a Internet. El proxy estático se puede configurar mediante la directiva de grupo (GP). La directiva de grupo se puede encontrar aquí:

- Plantillas administrativas \> Windows recopilación de datos y \> \> versiones preliminares Configurar el uso de proxy autenticado para el servicio de telemetría y experiencia del usuario conectado
- Estadíla en **Habilitada** y seleccione **Deshabilitar el uso de proxy autenticado**

1. Abra la Consola de administración de directivas de grupo.
2. Cree una directiva o edite una directiva existente basada en las prácticas organizativas.
3. Edite la directiva de grupo y vaya a **Plantillas \> administrativas Windows Componentes \> \> de recopilación de datos y versiones preliminares Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.

   ![Imagen de configuración de directiva de grupo.](images/atp-gpo-proxy1.png)

4. Seleccione **Habilitado**.
5. Seleccione **Deshabilitar el uso de proxy autenticado**.
6. Vaya a **Plantillas administrativas Windows \> de datos componentes \> y versiones preliminares Configure la telemetría y las experiencias \> de usuario conectadas**.

    ![Imagen de la configuración de directiva de grupo.](images/atp-gpo-proxy2.png)

7. Seleccione **Habilitado**.
8. Escriba el **nombre del servidor proxy**.

La directiva establece dos valores del registro `TelemetryProxyServer` como REG_SZ y `DisableEnterpriseAuthProxy` como REG_DWORD en la clave del registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.

El valor del Registro `TelemetryProxyServer` tiene el siguiente formato de cadena:

```text
<server name or ip>:<port>
```

Por ejemplo, 10.0.0.6:8080

El valor del registro `DisableEnterpriseAuthProxy` debe establecerse en 1.

### <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configurar el servidor proxy manualmente mediante el comando netsh

Use netsh para configurar un proxy estático en todo el sistema.

> [!NOTE]
>
> - Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.
> - Los portátiles que cambian la topología (por ejemplo: de la oficina a la casa) no funcionan correctamente con netsh. Use la configuración de proxy estático basada en el registro.

1. Abra un símbolo del sistema con privilegios elevados:
    1. Vaya a **Inicio** y escriba **cmd**.
    1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Por ejemplo: netsh winhttp set proxy 10.0.0.6:8080

### <a name="proxy-configuration-for-down-level-devices"></a>Configuración de proxy para dispositivos de nivel inferior

Down-Level incluyen Windows estaciones de trabajo de Windows 8.1 y 7 SP1, así como Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 y versiones de Windows Server 2016 anteriores a Windows  Servidor CB 1803. Estos sistemas operativos tendrán el proxy configurado como parte del Agente de administración de Microsoft para controlar la comunicación desde el punto de conexión a Azure. Consulte la Guía de implementación rápida de Microsoft Management Agent para obtener información sobre cómo se configura un proxy en estos dispositivos.

### <a name="proxy-service-urls"></a>Direcciones URL del servicio proxy

Las direcciones URL que incluyen v20 solo son necesarias si Windows 10, versión 1803 o Windows 11 dispositivos. Por ejemplo, `us-v20.events.data.microsoft.com` solo es necesario si el dispositivo está en Windows 10 versión 1803 o Windows 11.

Si un proxy o firewall bloquea el tráfico anónimo, ya que el sensor de Microsoft Defender para endpoint se conecta desde el contexto del sistema, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Asegúrese de que no hay reglas de filtrado de red o firewall que denieguen el *acceso a estas* direcciones URL, o puede que necesite crear una regla de permitido específicamente para ellas.

<br>

****


|Hoja de cálculo de la lista de dominios| Descripción|
|---|---|
|Lista de direcciones URL de Microsoft Defender para puntos de conexión para clientes comerciales | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes comerciales. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Lista de direcciones URL de punto de conexión de Microsoft Defender para clientes de Gov/GCC/DoD| Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sos para clientes gov/GCC/DoD. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)
|

## <a name="next-step"></a>Paso siguiente

![**Fase 3: Incorporación**.](images/onboard.png) <br> [Fase 3: Incorporación](onboarding.md) de dispositivos al servicio para que el servicio de Microsoft Defender para endpoints pueda obtener datos de sensores de ellos.
