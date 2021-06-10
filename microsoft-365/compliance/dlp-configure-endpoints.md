---
title: Herramientas y métodos de incorporación para dispositivos Windows 10
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
description: Incorporar Windows 10 dispositivos para que puedan enviar datos de sensor a las Microsoft 365 de cumplimiento normativo
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917856"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Herramientas y métodos de incorporación para dispositivos Windows 10

**Se aplica a:**
- [Microsoft 365 Prevención de pérdida de datos de extremo (DLP)](./endpoint-dlp-learn-about.md)

Los dispositivos de la organización deben configurarse para que Microsoft 365 servicio de prevención de pérdida de datos de punto de conexión pueda obtener datos de sensores de ellos. Existen varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de la organización.

Se admiten las siguientes herramientas y métodos de implementación:

- directiva de grupo
- Microsoft Endpoint Configuration Manager
- Administración de dispositivos móviles (Microsoft Intune)
- script local

## <a name="in-this-section"></a>En esta sección
Tema | Descripción
:---|:---
[Incorporación Windows 10 dispositivos con directiva de grupo](dlp-configure-endpoints-gp.md) | Use la directiva de grupo para implementar el paquete de configuración en dispositivos.
[Incorporar Windows dispositivos con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Puede usar Microsoft Endpoint Configuration Manager (rama actual) versión 1606 o Microsoft Endpoint Configuration Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en dispositivos.
[Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md) | Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.
[Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md) | Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md) | Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.