---
title: Permisos de características en EOP
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638123"
---
# <a name="feature-permissions-in-eop"></a>Permisos de características en EOP

Los permisos necesarios para realizar tareas para administrar Exchange Online Protection (EOP) varían en función de la característica que se administre.

Para configurar EOP, debe ser un administrador global o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización).

## <a name="exchange-online-protection-permissions"></a>Permisos de Protección en línea de Exchange

Para ver los permisos necesarios para administrar características de EOP, vea la siguiente tabla. Si una característica enumera más que un grupo de roles, solo tiene que estar asignado a uno de los grupos de roles para usarla.

|**Feature**|**Permisos necesarios**|
|:-----|:-----|
|Antimalware|Administración de la organización <br/><br/> Administración de higiene|
|Contra correo electrónico no deseado|Administración de la organización <br/><br/> Administración de higiene|
|Reglas de flujo de correo|Administración de la organización <br/><br/> Administración de registros|
|Dominios|Administración de la organización <br/><br/> Administración de la organización de solo visualización|
|Protección contra amenazas avanzada (ATP)|Administración de la organización <br/><br/> Administración de higiene|
|Conectores 365 de Microsoft|Administración de la organización|
|Seguimiento de mensajes|Administración de la organización <br/><br/> Administración de la organización de solo visualización|
|Configuración de la organización|Administración de la organización|
|Quarantine|Administración de la organización <br/><br/> Administración de la organización de solo visualización <br/><br/> Administración de higiene|
|Usuarios, contactos y grupos de roles|Administración de la organización <br/><br/> Administración de la organización de solo visualización <br/><br/> Administración de higiene|
|Grupos de distribución y grupos de seguridad|Administración de la organización <br/><br/> Administración de la organización de solo visualización <br/><br/> Administración de higiene|
|Ver informes|Administración de la organización: acceso a los informes de protección de correo. <br/><br/> View-Only Recipients: acceso a informes de protección de correo.  <br/><br/> Administración de cumplimiento: acceso a informes de protección de correo e informes de prevención de pérdida de datos (DLP) (si la suscripción tiene capacidades DLP).|
