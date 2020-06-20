---
title: Configurar usuarios y casos en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Obtenga información sobre cómo configurar roles de usuario, crear casos y asignar usuarios a los casos en la exhibición avanzada de documentos electrónicos.  '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6cfc8e313816c0c01512dd0d4b71f1dbbd6e6505
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819180"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>Configurar usuarios y casos en eDiscovery avanzado (Classic)

En este tema se describe cómo configurar usuarios y casos para la exhibición avanzada de documentos electrónicos (Classic).
  
> [!IMPORTANT]
> A medida que continuamos invirtiendo en nuevas versiones de eDiscovery avanzado, anunciamos la retirada de eDiscovery avanzado, también conocido como *eDiscovery avanzado (clásico)* o *eDiscovery avanzado v1.0* Si todavía está usando eDiscovery avanzado v1.0, cambie a [eDiscovery avanzado v2.0](overview-ediscovery-20.md) (también conocido como la *Solución de eDiscovery avanzado en Microsoft 365*) tan pronto como sea posible. eDiscovery avanzado 2.0 tiene funcionalidades similares a las que se encuentra en eDiscovery avanzado v1.0, pero también ofrece muchas características nuevas, como la administración de custodios, la administración de comunicaciones y los conjuntos de revisión. Para obtener más información sobre la retirada de eDiscovery avanzado v1.0, consulte [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 
  
## <a name="requirements-to-set-up-users-and-cases"></a>Requisitos para configurar usuarios y casos

Antes de configurar casos y usuarios en la exhibición avanzada de documentos electrónicos, se requiere lo siguiente:
  
- Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5. Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5. 
    
- Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento para crear un caso de exhibición de documentos electrónicos y agregarle miembros. Para agregarse al grupo de roles eDiscovery Manager en el &amp; centro de seguridad y cumplimiento, debe ser administrador global de la organización. Si no es un administrador global, deberá solicitar a un administrador global que le agregue al grupo de roles eDiscovery Manager. Para obtener más información, vea:
    
  - [Permisos en el centro de seguridad y cumplimiento de 365 de Microsoft &amp;](~/security/office-365-security/protect-against-threats.md)
    
  - [Asignar permisos de eDiscovery en el centro de seguridad y cumplimiento de 365 de Microsoft &amp;](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>Paso 1: asignar permisos de eDiscovery para los usuarios

El primer paso consiste en asignar a los usuarios los permisos de requisitos en el centro de seguridad y &amp; cumplimiento para que puedan agregarse como miembro de un caso de exhibición de documentos electrónicos. Una vez que un usuario se ha agregado como miembro de un caso en el centro de seguridad &amp; y cumplimiento, podrá obtener acceso al caso en la exhibición avanzada de documentos electrónicos.
  
Para asignar a un usuario los permisos necesarios para que se puedan agregar como miembro de un caso de exhibición de documentos electrónicos, vea el paso 1 en [casos de eDiscovery en el &amp; centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>Paso 2: crear un caso de exhibición de documentos electrónicos y agregar miembros

El siguiente paso consiste en crear un nuevo caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento y agregar miembros. Los miembros del caso podrán acceder al caso en la exhibición avanzada de documentos electrónicos.
  
1. Para crear un nuevo caso de exhibición de documentos electrónicos, vea el paso 3 en Introducción [a la exhibición](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)de documentos electrónicos principal.

2. Para agregar miembros a un caso de exhibición de documentos electrónicos, vea el paso 4 en Introducción [a la exhibición de](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case) documentos electrónicos principal

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>Paso 3: ir a un caso en eDiscovery avanzado

Después de crear un caso de exhibición de documentos electrónicos y agregar miembros, usted (o cualquier miembro del caso) puede tener acceso al caso correspondiente en eDiscovery avanzado. Para obtener acceso a un caso en la exhibición avanzada de documentos electrónicos, vea [obtener acceso a un caso en eDiscovery avanzado](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).
  
## <a name="see-also"></a>Vea también

[Advanced eDiscovery (clásico)](office-365-advanced-ediscovery.md)
  
[Preparar los datos para la exhibición avanzada de documentos electrónicos (Classic)](prepare-data-for-advanced-ediscovery.md)
 