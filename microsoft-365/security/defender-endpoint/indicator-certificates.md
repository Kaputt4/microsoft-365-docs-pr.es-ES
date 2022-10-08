---
title: Creación de indicadores basados en certificados
ms.reviewer: ''
description: Cree indicadores basados en certificados que definan la detección, prevención y exclusión de entidades.
keywords: ioc, certificate, certificates, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
- tier2
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ca15e36c0de968a2afddb14a5c8c74cffe969953
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232504"
---
# <a name="create-indicators-based-on-certificates"></a>Creación de indicadores basados en certificados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Puede crear indicadores para los certificados. Algunos casos de uso comunes incluyen:

- Escenarios en los que es necesario implementar tecnologías de bloqueo, como [reglas de reducción de superficie expuesta a ataques](attack-surface-reduction.md) y [acceso controlado a carpetas](controlled-folders.md) , pero es necesario permitir comportamientos de aplicaciones firmadas agregando el certificado en la lista de permitidos.
- Bloquear el uso de una aplicación firmada específica en toda la organización. Al crear un indicador para bloquear el certificado de la aplicación, Windows Defender AV impedirá las ejecuciones de archivos (bloquear y corregir) y la investigación y corrección automatizadas se comportarán igual.

## <a name="before-you-begin"></a>Antes de empezar

Es importante comprender los siguientes requisitos antes de crear indicadores de certificados:

- Esta característica está disponible si la organización usa Microsoft Defender Antivirus y la protección basada en la nube está habilitada. Para obtener más información, consulte [Administración de la protección basada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
- La versión de cliente de Antimalware debe ser 4.18.1901.x o posterior.
- Compatible con máquinas en Windows 10, versión 1703 o posterior, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2 y Windows Server 2022.
    
    >[!NOTE]
    >Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) para que esta característica funcione. 

- Las definiciones de protección contra virus y amenazas deben estar actualizadas.
- Actualmente, esta característica admite la introducción de . CER o . Extensiones de archivo PEM.

> [!IMPORTANT]
>
> - Un certificado hoja válido es un certificado de firma que tiene una ruta de certificación válida y se debe encadenar a la entidad de certificación raíz (CA) de confianza de Microsoft. Como alternativa, se puede usar un certificado personalizado (autofirmado) siempre que sea de confianza para el cliente (el certificado de entidad de certificación raíz está instalado en la máquina local "Entidades de certificación raíz de confianza").
> - Los elementos secundarios o primarios de los IOC de certificado de permitir o bloquear no se incluyen en la funcionalidad de IoC de permitir o bloquear, solo se admiten certificados hoja.
> - No se pueden bloquear los certificados firmados por Microsoft.

## <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Cree un indicador para los certificados desde la página de configuración:

> [!IMPORTANT]
> La creación y eliminación de un certificado IoC puede tardar hasta 3 horas.

1. En el panel de navegación, seleccione **Configuración** \> **Indicadores** de **puntos** \> de conexión (en **Reglas**).

2. Seleccione **Agregar indicador**.

3. Especifique los detalles siguientes:
   - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
   - Acción: especifique la acción que se va a realizar y proporcione una descripción.
   - Ámbito: defina el ámbito del grupo de máquinas.

4. Revise los detalles de la pestaña Resumen y haga clic en **Guardar**.

## <a name="related-topics"></a>Temas relacionados

- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para los archivos](indicator-file.md)
- [Crear indicadores para direcciones IP y URL/dominios](indicator-ip-domain.md)
- [Administrar indicadores](indicator-manage.md)
