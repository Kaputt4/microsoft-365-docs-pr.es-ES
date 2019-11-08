---
title: Permisos de características en EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Los permisos necesarios para hacer tareas de administración en Microsoft Exchange Online Protection (EOP) varían en función de la característica que se administre.
ms.openlocfilehash: e3b41ea2b58397a9af2a1cb8ba979b5f816b416b
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031915"
---
# <a name="feature-permissions-in-eop"></a>Permisos de características en EOP

Los permisos necesarios para realizar tareas para administrar Exchange Online Protection (EOP) varían en función de la característica que se administre.

Para configurar EOP debe ser un administrador global de Office 365 o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización).

## <a name="exchange-online-protection-permissions"></a>Permisos de Protección en línea de Exchange

Para ver los permisos necesarios para administrar características de EOP, vea la siguiente tabla. Si una característica enumera más que un grupo de roles, solo tiene que estar asignado a uno de los grupos de roles para usarla.

|**Feature**|**Permisos necesarios**|
|:-----|:-----|
|Antimalware|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Administración de higiene](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Contra correo electrónico no deseado|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Administración de higiene](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Reglas de flujo de correo|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](https://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx)|
|Dominios|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Protección contra amenazas avanzada (ATP)|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Administración de higiene](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Conectores de Office 365|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Seguimiento de mensajes|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Configuración de la organización|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Cuarentena|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Usuarios, contactos y grupos de roles|[Administración de organizaciones](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Grupos de distribución y grupos de seguridad|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Ver informes|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx): los usuarios tienen acceso a los informes de protección de correo.  <br/> [View-Only Recipients](https://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx): los usuarios tienen acceso a los informes de protección de correo.  <br/> [Compliance Management](https://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx): los usuarios tienen acceso a informes de protección de correo e informes de prevención de pérdida de datos (DLP) (si la suscripción tiene capacidades DLP).|
