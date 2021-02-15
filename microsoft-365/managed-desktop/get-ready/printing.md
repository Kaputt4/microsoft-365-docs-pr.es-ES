---
title: Preparar recursos de impresión para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de que la impresión funciona sin problemas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841404"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impresión para el Escritorio administrado de Microsoft

A medida que esté listo para inscribirse en el Escritorio administrado de Microsoft, debe evaluar los requisitos de impresión y determinar el enfoque adecuado para su entorno. Tiene tres opciones:
 
- Implemente la solución de impresión universal de Microsoft para que los dispositivos de escritorio administrado de Microsoft puedan detectar impresoras fácilmente. Para obtener más información, vea [¿Qué es impresión universal?](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)
- Implemente impresoras directamente mediante un script de PowerShell personalizado. Siga los pasos de la [sección Configurar impresoras](#set-up-local-printers) locales.
- Usa una solución de impresión en la nube que no sea de Microsoft que sea compatible con dispositivos con Windows 10 que estén unidos a un dominio de Azure Active Directory. La solución debe cumplir los requisitos de software del Escritorio administrado de Microsoft. Para obtener más información, vea [Los requisitos de la aplicación de Escritorio administrado de Microsoft.](../service-description/mmd-app-requirements.md)
 
En todos los casos, si los controladores de impresora no están disponibles desde Microsoft Update o Microsoft Store, tendrás que obtenerlos tú mismo y empaquetarlos para su implementación en los dispositivos de Escritorio administrado de Microsoft con Microsoft Intune. Para obtener más información, consulta [Intune independiente: administración de aplicaciones de Win32](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impresoras locales

Si ha decidido implementar impresoras con un script de PowerShell personalizado y ha preparado los recursos de impresión, siga estos pasos para implementar impresoras compartidas:

1.  Vaya al portal de Escritorio administrado de Microsoft.
2.  Envíe una solicitud con la etiqueta *Implementación* de impresora en la sección Solicitudes de soporte **técnico >** soporte técnico del Portal de administración, proporcionando estos detalles:
    - Todas las rutas de acceso UNC a ubicaciones de impresora compartidas que tendrán que implementarse para dispositivos de Escritorio administrado de Microsoft
    - Grupos de usuarios que requieren acceso a estas impresoras compartidas
3.  Con el Portal de administración, te haremos saber cuándo se ha completado la solicitud. Inicialmente, solo implementaremos la configuración en los dispositivos del grupo de implementación de prueba.
4.  Debe probar y confirmar si la configuración funciona de la forma esperada. Responda con la **pestaña Discusión** de la solicitud de soporte técnico para darnos cuenta cuando haya completado las pruebas.
5.  A continuación, implementaremos la configuración en los demás grupos de implementación.
