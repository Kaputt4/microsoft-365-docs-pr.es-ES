---
title: Crear indicadores para archivos
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
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199614"
---
# <a name="create-indicators-for-files"></a>Crear indicadores para archivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Puede evitar la propagación posterior de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso. Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo. Esta operación evitará que se lea, se escriba o se ejecute en equipos de la organización.

Hay dos formas de crear indicadores para archivos:
- Al crear un indicador a través de la página de configuración
- Al crear un indicador contextual mediante el botón agregar indicador desde la página de detalles del archivo

### <a name="before-you-begin"></a>Antes de empezar
Es importante comprender los siguientes requisitos previos antes de crear indicadores para archivos:

- Esta característica está disponible si su organización usa Windows Defender antivirus y la protección basada en la nube está habilitada. Para obtener más información, vea [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).
- La versión del cliente Antimalware debe ser 4.18.1901.x o posterior.
- Compatible con máquinas en Windows 10, versión 1703 o posterior, Windows Server 2016 y 2019.
- Para empezar a bloquear archivos, primero debe activar [la característica Bloquear **o**](advanced-features.md) permitir en Configuración.
- Esta característica está diseñada para evitar que el malware sospechoso (o los archivos potencialmente malintencionados) se descarguen de la web. Actualmente es compatible con archivos ejecutables portátiles (PE), incluidos los archivos _.exe_ y _.dll._ La cobertura se extenderá con el tiempo.

El rendimiento puede verse afectado si estás copiando archivos grandes de un recurso compartido de red en el dispositivo local, especialmente a través de una conexión VPN. 

> [!IMPORTANT]
> - La función permitir o bloquear no se puede realizar en archivos si la clasificación del archivo existe en la memoria caché del dispositivo antes de la acción permitir o bloquear 
> - Los archivos firmados de confianza se tratarán de forma diferente. Defender for Endpoint está optimizado para controlar archivos malintencionados. Intentar bloquear archivos firmados de confianza, en algunos casos, puede tener implicaciones en el rendimiento.
> - Normalmente, los bloques de archivos se aplican en un par de minutos, pero pueden tardar más de 30 minutos.
> - Si hay directivas de indicador de archivos en conflicto, se aplica la directiva de cumplimiento de la directiva más segura. Por ejemplo, una directiva de indicador hash de archivo SHA-256 tiene prioridad sobre una directiva de indicador de hash de archivo MD5 si ambos tipos de hash definen el mismo archivo.

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>Crear un indicador para archivos desde la página de configuración

1. En el panel de navegación, seleccione  >  **Indicadores de configuración**.  

2. Seleccione la **pestaña Hash de** archivo.

3. Seleccione **Agregar indicador**.

4. Especifique los siguientes detalles:
   - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
   - Action: especifique la acción que se va a realizar y proporcione una descripción.
   - Ámbito: defina el ámbito del grupo de máquinas.

5. Revise los detalles de la pestaña Resumen y, a continuación, haga clic **en Guardar**.

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Crear un indicador contextual desde la página de detalles del archivo
Una de las opciones al realizar acciones [de respuesta en un archivo](respond-file-alerts.md) es agregar un indicador para el archivo. 

Al agregar un hash de indicador para un archivo, puede optar por generar una alerta y bloquear el archivo siempre que un equipo de la organización intente ejecutarlo.

Los archivos bloqueados automáticamente por un indicador no aparecerán en el Centro de acciones del archivo, pero las alertas seguirán estando visibles en la cola de alertas.


## <a name="related-topics"></a>Temas relacionados
- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para direcciones IP y direcciones URL/dominios](indicator-ip-domain.md)
- [Crear indicadores basados en certificados](indicator-certificates.md)
- [Administrar indicadores](indicator-manage.md)
