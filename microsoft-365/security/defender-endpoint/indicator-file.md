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
ms.openlocfilehash: 32de72a201dbb88c9fc0c6d7e61825bf8083fbf9
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325549"
---
# <a name="create-indicators-for-files"></a>Crear indicadores para los archivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Impedir la propagación posterior de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso. Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo. Esta operación evitará que se lea, se escriba o se ejecute en dispositivos de la organización.

Hay tres formas de crear indicadores para archivos:

- Al crear un indicador a través de la página de configuración
- Al crear un indicador contextual mediante el botón agregar indicador desde la página de detalles del archivo
- Al crear un indicador a través de la [API de indicadores](ti-indicator.md)

## <a name="before-you-begin"></a>Antes de empezar

Es importante comprender los siguientes requisitos previos antes de crear indicadores para archivos:

- Esta característica está disponible si su organización usa Antivirus de Microsoft Defender **(en modo activo)** y la **protección basada en la nube está habilitada**. Para obtener más información, consulte [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).

- La versión del cliente Antimalware debe ser 4.18.1901.x o posterior. Ver [Versiones mensuales de la plataforma y el motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Compatible con dispositivos con Windows 10, versión 1703 o posterior, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2 y Windows Server 2022.
    
   >[!NOTE]
    >Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse con las instrucciones de [Onboard Windows servers](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) para que esta característica funcione. 

- Para empezar a bloquear archivos, primero debe activar [la característica "bloquear o permitir"](advanced-features.md) en Configuración.

Esta característica está diseñada para evitar que el malware sospechoso (o los archivos potencialmente malintencionados) se descarguen de la web. Actualmente es compatible con archivos ejecutables portátiles (PE), incluidos .exe archivos .dll archivos. La cobertura se extenderá con el tiempo.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Crear un indicador para archivos desde la página de configuración

1. En el panel de navegación, **seleccione Configuración** \> **indicadores** \> **de puntos de conexión** (en **Reglas**).

2. Seleccione la **pestaña Hashes de** archivo.

3. Seleccione **Agregar elemento**.

4. Especifique los siguientes detalles:
    - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
    - Action: especifique la acción que se va a realizar y proporcione una descripción.
    - Ámbito: defina el ámbito del grupo de dispositivos.

5. Revise los detalles de la pestaña Resumen y, a continuación, **seleccione Guardar**.

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Crear un indicador contextual desde la página de detalles del archivo

Una de las opciones al realizar acciones [de respuesta en un archivo](respond-file-alerts.md) es agregar un indicador para el archivo. Cuando agregas un hash de indicador para un archivo, puedes elegir generar una alerta y bloquear el archivo siempre que un dispositivo de la organización intente ejecutarlo.

Los archivos bloqueados automáticamente por un indicador no aparecerán en el Centro de acciones del archivo, pero las alertas seguirán estando visibles en la cola de alertas.

## <a name="public-preview-alerting-on-file-blocking-actions"></a>Vista previa pública: Alertar sobre acciones de bloqueo de archivos

> [!IMPORTANT]
> La información de esta sección (**Public Preview for Automated investigation and remediation engine**) se relaciona con el producto de versión preliminar que podría modificarse considerablemente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Las acciones actuales admitidas para el IOC de archivos son permitir, auditar y bloquear y corregir. Después de elegir bloquear un archivo, puede elegir si es necesario activar una alerta. De este modo, podrá controlar el número de alertas que se van a recibir en los equipos de operaciones de seguridad y asegurarse de que solo se generarán las alertas necesarias.

En Microsoft 365 Defender, vaya **a Configuración** >  **EndpointsIndicatorsAdd** >  >  **New File Hash**.

Elija Bloquear y corregir el archivo.

Elija si desea generar una alerta en el evento de bloqueo de archivos y definir la configuración de alertas:

- El título de alerta
- Gravedad de la alerta
- Categoría
- Descripción
- Acciones recomendadas

![Configuración de alertas para indicadores de archivo.](images/indicators-generate-alert.png)

> [!IMPORTANT]
>
> - Normalmente, los bloques de archivos se aplican y se quitan en un par de minutos, pero pueden tardar más de 30 minutos.
> - Si hay directivas de IoC de archivos en conflicto con el mismo tipo de aplicación y destino, se aplicará la directiva del hash más seguro. Una directiva de IoC de hash de archivo SHA-256 ganará una directiva de IoC de hash de archivo SHA-1, que ganará una directiva de IoC de hash de archivo MD5 si los tipos hash definen el mismo archivo. Esto siempre es así independientemente del grupo de dispositivos.
> - En todos los demás casos, si las directivas de IoC de archivos en conflicto con el mismo destino de aplicación se aplican a todos los dispositivos y al grupo del dispositivo, en el caso de un dispositivo, la directiva del grupo de dispositivos ganará.
> - Si la directiva de grupo EnableFileHashComputation está deshabilitada, se reduce la precisión de bloqueo del archivo IoC. Sin embargo, la habilitación `EnableFileHashComputation` puede afectar al rendimiento del dispositivo. Por ejemplo, copiar archivos grandes de un recurso compartido de red en el dispositivo local, especialmente a través de una conexión VPN, puede tener un efecto en el rendimiento del dispositivo.
>
> Para obtener más información acerca de la directiva de grupo EnableFileHashComputation, vea [Defender CSP](/windows/client-management/mdm/defender-csp).

## <a name="public-preview-advanced-hunting-capabilities"></a>Vista previa pública: capacidades avanzadas de búsqueda

> [!IMPORTANT]
> La información de esta sección (**Public Preview for Automated investigation and remediation engine**) se relaciona con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Puede consultar la actividad de acción de respuesta en la búsqueda previa. A continuación se muestra una consulta de búsqueda anticipada de ejemplo:

```console
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
Timestamp > ago(30d)
| where AdditionalFields contains "EUS:Win32/CustomEnterpriseBlock!cl"
```

Para obtener más información acerca de la búsqueda avanzada, vea [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).

A continuación se muestran nombres de subprocesos adicionales que se pueden usar en la consulta de ejemplo de arriba:

Archivos:

- EUS:Win32/CustomEnterpriseBlock!cl
- EUS:Win32/CustomEnterpriseNoAlertBlock!cl

Certificados:

- EUS:Win32/CustomCertEnterpriseBlock!cl

La actividad de acción de respuesta también se puede ver en la escala de tiempo del dispositivo.

## <a name="policy-conflict-handling"></a>Control de conflictos de directivas

Los conflictos de administración de directivas de Cert y File IoC seguirán el siguiente orden:

- Si el archivo no está permitido por Windows Defender control de aplicaciones y AppLocker aplican directivas o directivas de modo, **bloquee**
- Si el archivo está permitido por la exclusión Antivirus de Microsoft Defender **, permitir**
- De lo contrario, si un bloqueo o un archivo de advertencia bloquean o advierten el archivo IoC, **bloquee o advierte el archivo**.
- De lo contrario, si el archivo está permitido por una directiva de IoC de archivo de permitido **, permitir**
- De lo contrario, si el archivo está bloqueado por reglas ASR, CFA, AV, SmartScreen y, a continuación, **Bloquear**
- Else **Allow** (pasa Windows Defender application control & directiva de AppLocker, no se aplican reglas de IoC a ella)

>[!NOTE]
> En situaciones en las que Antivirus de Microsoft Defender está establecido en **Bloquear**, pero Defender para extremo está establecido en **Permitir**, la directiva se establecerá de forma **predeterminada en Permitir**.

Si hay directivas de IoC de archivos en conflicto con el mismo tipo de aplicación y destino, se aplicará la directiva del hash más seguro (es decir, más largo). Por ejemplo, una directiva de IoC de hash de archivo SHA-256 ganará una directiva de IoC de hash de archivo MD5 si ambos tipos de hash definen el mismo archivo.

> [!WARNING]
> El control de conflictos de directivas para archivos y certificados difiere del control de conflictos de directivas para dominios/DIRECCIONES URL/direcciones IP.

Las características de aplicación vulnerables de bloqueo de administración de vulnerabilidades y amenazas usan el archivo IoCs para la aplicación y seguirán el orden de control de conflictos anterior.

### <a name="examples"></a>Ejemplos

<br>

****

|Componente|Aplicación de componentes|Indicador de archivo Acción|Resultado|
|---|---|---|---|
|Exclusión de ruta de acceso de archivo de reducción de superficie de ataque|Permitir|Bloquear|Bloquear|
|Regla de reducción de superficie de ataque|Bloquear|Permitir|Permitir|
|Control de aplicaciones de Windows Defender|Permitir|Bloquear|Permitir|
|Control de aplicaciones de Windows Defender|Bloquear|Permitir|Bloquear|
|Antivirus de Microsoft Defender exclusión|Permitir|Bloquear|Permitir|
|

## <a name="see-also"></a>Vea también

- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para direcciones IP y URL/dominios](indicator-ip-domain.md)
- [Crear indicadores basados en certificados](indicator-certificates.md)
- [Administrar indicadores](indicator-manage.md)
