---
title: Herramientas y métodos de incorporación para dispositivos Windows 10 (versión preliminar)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Dispositivos de Windows 10 incorporados para que puedan enviar datos del sensor a las soluciones de cumplimiento de Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769647"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Herramientas y métodos de incorporación para dispositivos Windows 10 (versión preliminar)

**Se aplica a:**
- [Prevención de pérdida de datos (DLP) de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

Los dispositivos de la organización deben configurarse para que el servicio de prevención de pérdida de datos de extremos de Microsoft 365 pueda obtener datos de los sensores. Hay varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de su organización.

Se admiten las siguientes herramientas y métodos de implementación:

- Directiva de grupo
- Microsoft Endpoint Configuration Manager
- Administración de dispositivos móviles (incluido Microsoft Intune)
- script local

## <a name="in-this-section"></a>En esta sección
Tema | Descripción
:---|:---
[Dispositivos de Windows 10 incorporados mediante la Directiva de grupo](dlp-configure-endpoints-gp.md) | Use la Directiva de grupo para implementar el paquete de configuración en dispositivos.
[Dispositivos Windows incorporados mediante el administrador de configuración de Microsoft Endpoint](dlp-configure-endpoints-sccm.md) | Puede usar usar Microsoft Endpoint Configuration Manager (rama actual) versión 1606 o Microsoft Endpoint Configuration Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en los dispositivos.
[Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles](dlp-configure-endpoints-mdm.md) | Use las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.
[Dispositivos de Windows 10 incorporados que usan un script local](dlp-configure-endpoints-script.md) | Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados](dlp-configure-endpoints-vdi.md) | Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.
