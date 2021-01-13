---
title: Tecnologías del Escritorio administrado de Microsoft
description: En este artículo se enumeran las tecnologías y aplicaciones usadas en el Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840906"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías del Escritorio administrado de Microsoft

En este artículo se enumeran las tecnologías y aplicaciones usadas en el Escritorio administrado de Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Las licencias de Microsoft 365 Enterprise son necesarias para todos los usuarios de Escritorio administrado de Microsoft. Para obtener más información sobre los requisitos de licencia para el servicio, vea [Requisitos previos para escritorio administrado de Microsoft.](../get-ready/prerequisites.md)

En este artículo se resumen los componentes incluidos en las licencias enterprise necesarias, con una descripción de cómo el servicio usa cada componente con dispositivos de Escritorio administrado de Microsoft. Los roles y responsabilidades específicos de cada área se detallan en toda la documentación de Escritorio administrado de Microsoft. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5
 |
 --- | ---
Aplicaciones de Microsoft 365 para empresas (64 bits) | Estas aplicaciones de Office se enviarán con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial y OneNote.<br><br>No se incluyen las versiones completas de 64 bits de Microsoft Project y Microsoft Visio. Sin embargo, dado que la instalación de estas aplicaciones depende de la instalación de Aplicaciones de Microsoft 365 para empresas, Escritorio administrado de Microsoft ha creado implementaciones predeterminadas de Microsoft Intune y grupos de seguridad que puede usar para implementar estas aplicaciones en usuarios con licencia. Para obtener más información, vea [Instalar Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft.](../get-started/project-visio.md)
OneDrive |El inicio de sesión único de Azure Active Directory está habilitado para los usuarios cuando inician sesión por primera vez en OneDrive.<br><br>Se incluye el redireccionamiento de carpetas conocidas para las carpetas "Escritorio", "Documento" e "Imágenes"; habilitado y configurado por escritorio administrado de Microsoft.
Aplicaciones de la Tienda |    Microsoft Sway y Power BI no se envían con el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones de Win32 |    Teams no se incluye con el dispositivo, pero microsoft los empaqueta y proporciona para los dispositivos de escritorio administrado de Microsoft. El cliente de Azure Information Protection no se incluye con el dispositivo, pero se puede empaquetar para su implementación.
Aplicaciones web |  Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps y Planner no se envían con el dispositivo. Los usuarios pueden acceder a la versión web de estas aplicaciones con un explorador.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender para puntos de conexión

 |
 --- | ---
Virtualización de aplicaciones (App-V) |    Los clientes pueden implementar paquetes de App-V con el cliente de administración de aplicaciones de Intune Win32.
Microsoft Defender para punto de conexión |    Escritorio administrado de Microsoft usa este producto para supervisar la seguridad del dispositivo. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puedes usar todas las características de Enterprise Mobility + Security E3 y Azure Active Directory Premium P2 para administrar dispositivos MDM.
Microsoft Cloud App Security |  Puede usar esta característica opcional con escritorio administrado de Microsoft.
Azure Information Protection P2  | Puede usar esta característica opcional con escritorio administrado de Microsoft.
