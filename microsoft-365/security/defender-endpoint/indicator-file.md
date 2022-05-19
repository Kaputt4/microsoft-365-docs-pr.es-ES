---
title: Crear indicadores para los archivos
ms.reviewer: ''
description: Cree indicadores para un hash de archivo que defina la detección, prevención y exclusión de entidades.
keywords: file, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: da9e030d929f65c7ea5bd83010d2b7f49b1d90d9
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535600"
---
# <a name="create-indicators-for-files"></a>Crear indicadores para los archivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

> [!TIP]
> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Evite la propagación de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o sospechas de malware. Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo. Esta operación impedirá que se lea, escriba o ejecute en dispositivos de su organización.

Hay tres maneras de crear indicadores para los archivos:

- Mediante la creación de un indicador a través de la página de configuración
- Mediante la creación de un indicador contextual con el botón agregar indicador desde la página de detalles del archivo
- Mediante la creación de un indicador a través de indicator [API](ti-indicator.md)

## <a name="before-you-begin"></a>Antes de empezar

Es importante comprender los siguientes requisitos previos antes de crear indicadores para los archivos:

- Esta característica está disponible si su organización usa **Antivirus de Microsoft Defender (en modo activo)** y **la protección basada en la nube está habilitada**. Para obtener más información, consulte [Administración de la protección basada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).

- La versión de cliente de Antimalware debe ser 4.18.1901.x o posterior. Consulte [Versiones mensuales de la plataforma y del motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Compatible con dispositivos con Windows 10, versión 1703 o posterior, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2 y Windows Server 2022.
    
   > [!NOTE]
   > Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) para que esta característica funcione. Los indicadores de archivos personalizados con las acciones Permitir, Bloquear y Corregir ahora también están disponibles en la [versión preliminar pública para las funcionalidades mejoradas del motor antimalware para macOS y Linux](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-engine-capabilities-for-linux-and-macos/ba-p/3292003).

- Para empezar a bloquear archivos, primero debe [activar la característica "bloquear o permitir"](advanced-features.md) en Configuración.

Esta característica está diseñada para evitar que se descargue malware sospechoso (o archivos potencialmente malintencionados) desde la web. Actualmente admite archivos ejecutables portátiles (PE), incluidos los archivos .exe y .dll. La cobertura se ampliará con el tiempo.

> [!IMPORTANT]
> En El plan 1 de Defender para punto de conexión y Defender para empresas, puede crear un indicador para bloquear o permitir un archivo. En Defender para empresas, el indicador se aplica en todo el entorno y no se puede limitar a dispositivos específicos.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Creación de un indicador para archivos desde la página de configuración

1. En el panel de navegación, seleccione **Configuración** \> **Indicadores** \> de **puntos de conexión** (en **Reglas**).

2. Seleccione la pestaña **Hashes de archivo** .

3. Seleccione **Agregar elemento**.

4. Especifique los detalles siguientes:
    - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
    - Acción: especifique la acción que se va a realizar y proporcione una descripción.
    - Ámbito: defina el ámbito del grupo de dispositivos (el ámbito no está disponible en [Defender para empresas](../defender-business/mdb-overview.md)).

5. Revise los detalles de la pestaña Resumen y, a continuación, seleccione **Guardar**.

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Creación de un indicador contextual desde la página de detalles del archivo

Una de las opciones al realizar [acciones de respuesta en un archivo](respond-file-alerts.md) es agregar un indicador para el archivo. Al agregar un hash de indicador para un archivo, puede optar por generar una alerta y bloquear el archivo cada vez que un dispositivo de su organización intente ejecutarlo.

Los archivos bloqueados automáticamente por un indicador no se mostrarán en el Centro de acciones del archivo, pero las alertas seguirán siendo visibles en la cola Alertas.

## <a name="public-preview-alerting-on-file-blocking-actions"></a>Versión preliminar pública: alertas sobre las acciones de bloqueo de archivos

> [!IMPORTANT]
> La información de esta sección (**versión preliminar pública para el motor de investigación y corrección automatizada**) se refiere al producto de versión preliminar que podría modificarse sustancialmente antes de que se publique comercialmente. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Las acciones admitidas actuales para la IOC de archivos son permitir, auditar y bloquear y corregir. Después de elegir bloquear un archivo, puede elegir si se necesita desencadenar una alerta. De este modo, podrá controlar el número de alertas que reciben los equipos de operaciones de seguridad y asegurarse de que solo se generan las alertas necesarias.

En Microsoft 365 Defender, vaya a **Configuración** >  EndpointsIndicatorsAgregar >  >  **nuevo hash de archivo**.

Elija Bloquear y corregir el archivo.

Elija si desea Generar una alerta en el evento de bloque de archivos y defina la configuración de alertas:

- El título de la alerta
- Gravedad de la alerta
- Categoría
- Descripción
- Acciones recomendadas

:::image type="content" source="images/indicators-generate-alert.png" alt-text="Configuración de alertas para los indicadores de archivo" lightbox="images/indicators-generate-alert.png":::

> [!IMPORTANT]
>
> - Normalmente, los bloques de archivos se aplican y quitan en un par de minutos, pero pueden tardar más de 30 minutos.
> - Si hay directivas de IoC de archivos en conflicto con el mismo tipo de cumplimiento y destino, se aplicará la directiva del hash más seguro. Una directiva ioC de hash de archivo SHA-256 ganará una directiva ioC de hash de archivo SHA-1, que ganará una directiva ioC de hash de archivo MD5 si los tipos hash definen el mismo archivo. Esto siempre es cierto independientemente del grupo de dispositivos.
> - En todos los demás casos, si se aplican directivas de IoC de archivos en conflicto con el mismo destino de cumplimiento a todos los dispositivos y al grupo del dispositivo, en el caso de un dispositivo, la directiva del grupo de dispositivos ganará.
> - Si la directiva de grupo EnableFileHashComputation está deshabilitada, se reduce la precisión de bloqueo del archivo IoC. Sin embargo, la habilitación `EnableFileHashComputation` puede afectar al rendimiento del dispositivo. Por ejemplo, la copia de archivos grandes de un recurso compartido de red en el dispositivo local, especialmente a través de una conexión VPN, podría tener un efecto en el rendimiento del dispositivo.
>
> Para obtener más información sobre la directiva de grupo EnableFileHashComputation, consulte [CSP de Defender](/windows/client-management/mdm/defender-csp).

## <a name="public-preview-advanced-hunting-capabilities"></a>Versión preliminar pública: funcionalidades avanzadas de búsqueda

> [!IMPORTANT]
> La información de esta sección (**versión preliminar pública para el motor de investigación y corrección automatizada**) se refiere al producto de versión preliminar que se puede modificar sustancialmente antes de que se publique comercialmente. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Puede consultar la actividad de acción de respuesta en la búsqueda anticipada. A continuación se muestra una consulta de búsqueda anticipada de ejemplo:

```console
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
Timestamp > ago(30d)
| where AdditionalFields contains "EUS:Win32/CustomEnterpriseBlock!cl"
```

Para obtener más información sobre la búsqueda avanzada, vea [Búsqueda proactiva de amenazas con búsqueda avanzada](advanced-hunting-overview.md).

A continuación se muestran nombres de subproceso adicionales que se pueden usar en la consulta de ejemplo anterior:

Archivos:

- EUS:Win32/CustomEnterpriseBlock!cl
- EUS:Win32/CustomEnterpriseNoAlertBlock!cl

Certificados:

- EUS:Win32/CustomCertEnterpriseBlock!cl

La actividad de acción de respuesta también se puede ver en la escala de tiempo del dispositivo.

## <a name="policy-conflict-handling"></a>Control de conflictos de directivas

El control de directivas de IoC de certificados y archivos seguirá el orden siguiente:

- Si el archivo no está permitido por Windows Defender directivas o directivas de aplicación de Application Control y AppLocker, **bloquee**
- De lo contrario, si el archivo está permitido por la exclusión de Antivirus de Microsoft Defender **, permitir**
- De lo contrario, si el archivo está bloqueado o advertido por un bloque o un archivo de advertencia IoC, **bloquee o advierta**.
- De lo contrario, si se permite el archivo mediante una directiva de IoC de archivo permitido **, permitir**
- De lo contrario, si el archivo está bloqueado por reglas de ASR, CFA, AV, SmartScreen y, a continuación, **Bloquear**
- De lo contrario **, permitir** (pasa Windows Defender control de aplicaciones & directiva de AppLocker, no se le aplican reglas de IoC)

>[!NOTE]
> En situaciones en las que Antivirus de Microsoft Defender se establece en **Bloquear**, pero Defender para punto de conexión está establecido en **Permitir**, la directiva tendrá como valor predeterminado **Permitir**.

Si hay directivas de IoC de archivos en conflicto con el mismo tipo de cumplimiento y destino, se aplicará la directiva del hash más seguro (es decir, más largo). Por ejemplo, una directiva ioC de hash de archivo SHA-256 obtendrá una directiva ioC de hash de archivo MD5 si ambos tipos hash definen el mismo archivo.

> [!WARNING]
> El control de conflictos de directivas para archivos y certificados difiere del control de conflictos de directivas para dominios, direcciones URL o direcciones IP.

Las características de aplicación vulnerables a bloques de amenazas y administración de vulnerabilidades usan los ioC de archivo para la aplicación y seguirán el orden de control de conflictos anterior.

### <a name="examples"></a>Ejemplos

<br>

****

|Componente|Aplicación de componentes|Acción del indicador de archivo|Resultado|
|---|---|---|---|
|Exclusión de la ruta de acceso del archivo de reducción de superficie expuesta a ataques|Permitir|Bloquear|Bloquear|
|Regla de reducción de superficie expuesta a ataques|Bloquear|Permitir|Permitir|
|Control de aplicaciones de Windows Defender|Permitir|Bloquear|Permitir|
|Control de aplicaciones de Windows Defender|Bloquear|Permitir|Bloquear|
|exclusión de Antivirus de Microsoft Defender|Permitir|Bloquear|Permitir|
|

## <a name="see-also"></a>Consulte también

- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para direcciones IP y URL/dominios](indicator-ip-domain.md)
- [Creación de indicadores basados en certificados](indicator-certificates.md)
- [Administrar indicadores](indicator-manage.md)
