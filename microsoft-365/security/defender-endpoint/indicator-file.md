---
title: Crear indicadores para los archivos
ms.reviewer: ''
description: Cree indicadores para un hash de archivo que defina la detección, prevención y exclusión de entidades.
keywords: file, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730539"
---
# <a name="create-indicators-for-files"></a>Crear indicadores para los archivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Impedir la propagación posterior de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso. Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo. Esta operación evitará que se lea, se escriba o se ejecute en dispositivos de la organización.

Hay tres formas de crear indicadores para archivos:

- Al crear un indicador a través de la página de configuración
- Al crear un indicador contextual mediante el botón agregar indicador desde la página de detalles del archivo
- Al crear un indicador a través de la [API de indicadores](ti-indicator.md)

## <a name="before-you-begin"></a>Antes de empezar

Es importante comprender los siguientes requisitos previos antes de crear indicadores para archivos:

- Esta característica está disponible si su organización usa **Antivirus de Microsoft Defender (en** modo activo) y la **protección basada en la nube está habilitada.** Para obtener más información, vea [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).

- La versión del cliente Antimalware debe ser 4.18.1901.x o posterior. Ver [Versiones mensuales de la plataforma y el motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Compatible con dispositivos con Windows 10, versión 1703 o posterior, Windows Server 2016 y 2019.

- Para empezar a bloquear archivos, primero debe activar [la característica "bloquear](advanced-features.md) o permitir" en Configuración.

Esta característica está diseñada para evitar que el malware sospechoso (o los archivos potencialmente malintencionados) se descarguen de la web. Actualmente es compatible con archivos ejecutables portátiles (PE), incluidos .exe archivos .dll archivos. La cobertura se extenderá con el tiempo.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Crear un indicador para archivos desde la página de configuración

1. En el panel de navegación, **seleccione Configuración > Indicadores**.

2. Seleccione la **pestaña Hash de**   archivo.

3. Seleccione **Agregar indicador**.

4. Especifique los siguientes detalles:
    - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
    - Action: especifique la acción que se va a realizar y proporcione una descripción.
    - Ámbito: defina el ámbito del grupo de dispositivos.

5. Revise los detalles de la pestaña Resumen y, a continuación, **seleccione Guardar**.

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Crear un indicador contextual desde la página de detalles del archivo

Una de las opciones al realizar acciones [de respuesta en un archivo](respond-file-alerts.md)es agregar un indicador para el   archivo. Cuando agregas un hash de indicador para un archivo, puedes elegir generar una alerta y bloquear el archivo siempre que un dispositivo de la organización intente ejecutarlo.

Los archivos bloqueados automáticamente por un indicador no aparecerán en el Centro de acciones del archivo, pero las alertas seguirán estando visibles en la cola de alertas.

>[!IMPORTANT]
>- Normalmente, los bloques de archivos se aplican y se quitan en un par de minutos, pero pueden tardar más de 30 minutos.
>- Si hay directivas de indicador de archivos en conflicto, se aplica la directiva de cumplimiento de la directiva más segura. Por ejemplo, una directiva de indicador hash de archivo SHA-256 tiene prioridad sobre una directiva de indicador de hash de archivo MD5 si ambos tipos de hash definen el mismo archivo.
>- Si la directiva de grupo EnableFileHashComputation está deshabilitada, se reduce la precisión de bloqueo del archivo IoC. Sin embargo, habilitar EnableFileHashComputation puede afectar al rendimiento del dispositivo.
>    - Por ejemplo, copiar archivos grandes de un recurso compartido de red en el dispositivo local, especialmente a través de una conexión VPN, puede tener un efecto en el rendimiento del dispositivo.
>    - Para obtener más información acerca de la directiva de grupo EnableFileHashComputation, vea [Defender CSP](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>Control de conflictos de directivas  

Los conflictos de administración de directivas de Cert y File IoC seguirán el siguiente orden:

- Si el archivo no está permitido por Windows Defender control de aplicaciones y AppLocker aplican directivas o directivas de modo, **bloquee**

- Si el archivo está permitido por la exclusión Antivirus de Microsoft Defender, **permitir**

- De lo contrario, si un bloqueo o un archivo de advertencia bloquean o advierten el archivo IoC, **bloquee o advierte el archivo.**

- De lo contrario, si el archivo está permitido por una directiva de IoC de archivo de permitido, **permitir**

- De lo contrario, si el archivo está bloqueado por reglas ASR, CFA, AV, SmartScreen y, a continuación, **Bloquear**  

- Else **Allow** (pasa Windows Defender control de & directiva de AppLocker, no se aplica ninguna regla de IoC)

Si hay directivas de IoC de archivos en conflicto con el mismo tipo de aplicación y destino, se aplicará la directiva del hash más seguro (es decir, más largo). Por ejemplo, una directiva de IoC de hash de archivo SHA-256 ganará una directiva de IoC de hash de archivo MD5 si ambos tipos de hash definen el mismo archivo.

Tenga en cuenta que Administración de amenazas y vulnerabilidades aplicaciones vulnerables de bloqueo de la aplicación usa el archivo IoCs para la aplicación y seguirá el orden de control de conflictos anterior.

### <a name="examples"></a>Ejemplos

|Componente |Aplicación de componentes |Indicador de archivo Acción |Resultado
|--|--|--|--|
|Exclusión de ruta de acceso de archivo de reducción de superficie de ataque |Permitir |Bloquear |Bloquear
|Regla de reducción de superficie de ataque |Bloquear |Permitir |Permitir
|Control de aplicaciones de Windows Defender |Permitir |Bloquear |Permitir |
|Control de aplicaciones de Windows Defender |Bloquear |Permitir |Bloquear
|Antivirus de Microsoft Defender exclusión |Permitir |Bloquear |Permitir

## <a name="see-also"></a>Consulte también

- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para direcciones IP y URL/dominios](indicator-ip-domain.md)
- [Crear indicadores basados en certificados](indicator-certificates.md)
- [Administrar indicadores](indicator-manage.md)
