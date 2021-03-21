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
ms.openlocfilehash: 3decc7d67decc5557e7921e68108e2ddb447f0fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924557"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impresión para el Escritorio administrado de Microsoft

A medida que esté listo para inscribirse en Microsoft Managed Desktop, debe evaluar los requisitos de impresión y determinar el enfoque adecuado para su entorno. Tiene tres opciones:
 
- Implemente la solución de impresión universal de Microsoft para facilitar que los dispositivos de Escritorio administrado de Microsoft detecte impresoras. Para obtener más información, vea [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).
- Implemente impresoras directamente mediante un script de PowerShell personalizado. Siga los pasos de la [sección Configurar impresoras](#set-up-local-printers) locales.
- Use una solución de impresión en la nube que no sea de Microsoft que sea compatible con dispositivos Windows 10 unidos a un dominio de Azure Active Directory. La solución debe cumplir los requisitos de software para Microsoft Managed Desktop. Para obtener más información, consulta [Requisitos de la aplicación de Escritorio administrado de Microsoft.](../service-description/mmd-app-requirements.md)
 
En todos los casos, si los controladores de impresora no están disponibles en Microsoft Update o microsoft Store, tendrás que obtenerlos tú mismo y empaquetarlos para su implementación en los dispositivos de Escritorio administrado de Microsoft con Microsoft Intune. Para obtener más información, [consulta Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impresoras locales

Si ha decidido implementar impresoras mediante un script de PowerShell personalizado y ha preparado los recursos de impresión, siga estos pasos para que las impresoras compartidas se implementen:

1.  Vaya al portal de Escritorio administrado de Microsoft.
2.  Envíe una solicitud con la etiqueta *Implementación* de impresora en la sección Solicitudes de soporte **> soporte** técnico del Portal de administración, proporcionando estos detalles:
    - Todas las rutas de acceso UNC a ubicaciones de impresora compartidas que tendrán que implementarse para dispositivos de Escritorio administrado de Microsoft
    - Grupos de usuarios que requieren acceso a estas impresoras compartidas
3.  Con el Portal de administración, le haremos saber cuándo se ha completado la solicitud. Inicialmente, solo implementaremos la configuración en los dispositivos del grupo de implementación de prueba.
4.  Debe probar y confirmar si la configuración funciona como espera. Responda mediante la pestaña **Discusión** de la solicitud de soporte técnico para que sepamos cuándo ha completado las pruebas.
5.  A continuación, implementaremos la configuración en los otros grupos de implementación.