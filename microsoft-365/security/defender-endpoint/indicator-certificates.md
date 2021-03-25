---
title: Crear indicadores basados en certificados
ms.reviewer: ''
description: Cree indicadores basados en certificados que definan la detección, prevención y exclusión de entidades.
keywords: ioc, certificate, certificates, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164686"
---
# <a name="create-indicators-based-on-certificates"></a>Crear indicadores basados en certificados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Puede crear indicadores para certificados. Algunos casos de uso comunes incluyen:

- Escenarios en los que necesitas implementar [](attack-surface-reduction.md) tecnologías de [](controlled-folders.md) bloqueo, como reglas de reducción de superficie de ataque y acceso controlado a carpetas, pero necesitas permitir comportamientos de aplicaciones firmadas agregando el certificado en la lista de permitidos.
- Bloquear el uso de una aplicación firmada específica en toda la organización. Al crear un indicador para bloquear el certificado de la aplicación, Windows Defender AV evitará las ejecuciones de archivos (bloquear y corregir) y la investigación y corrección automatizadas se comportan igual.


### <a name="before-you-begin"></a>Antes de empezar

Es importante comprender los siguientes requisitos antes de crear indicadores para certificados:

- Esta característica está disponible si su organización usa Windows Defender antivirus y la protección basada en la nube está habilitada. Para obtener más información, vea [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
- La versión del cliente Antimalware debe ser 4.18.1901.x o posterior.
- Compatible con máquinas en Windows 10, versión 1703 o posterior, Windows Server 2016 y 2019.
- Las definiciones de protección contra virus y amenazas deben estar actualizadas.
- Actualmente, esta característica admite la introducción de . CER o . Extensiones de archivo PEM.

>[!IMPORTANT]
> - Un certificado hoja válido es un certificado de firma que tiene una ruta de certificación válida y se debe encadenar a la entidad de certificación raíz (CA) de confianza de Microsoft.  Como alternativa, se puede usar un certificado personalizado (autofirmado) siempre que sea de confianza para el cliente (el certificado de entidad de certificación raíz está instalado en la máquina local "Entidades de certificación raíz de confianza").
>- Los elementos secundarios o primarios de los EIC de certificado de permitir o bloquear no se incluyen en la funcionalidad de IoC de permitir o bloquear, solo se admiten certificados hoja.
>- Los certificados firmados por Microsoft no se pueden bloquear.

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Cree un indicador para certificados desde la página de configuración:

>[!IMPORTANT]
> Puede tardar hasta 3 horas en crear y quitar un certificado IoC.

1. En el panel de navegación, seleccione  >  **Indicadores de configuración**.  

2. Seleccione la **pestaña** Certificado.

3. Seleccione **Agregar indicador**.

4. Especifique los siguientes detalles:
   - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
   - Action: especifique la acción que se va a realizar y proporcione una descripción.
   - Ámbito: defina el ámbito del grupo de máquinas.

5. Revise los detalles de la pestaña Resumen y, a continuación, haga clic **en Guardar**.

## <a name="related-topics"></a>Temas relacionados
- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para archivos](indicator-file.md)
- [Crear indicadores para direcciones IP y direcciones URL/dominios](indicator-ip-domain.md)
- [Administrar indicadores](indicator-manage.md)
