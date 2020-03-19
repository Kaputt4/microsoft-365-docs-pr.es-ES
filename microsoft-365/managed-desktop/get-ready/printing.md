---
title: Preparar recursos de impresión para el escritorio administrado por Microsoft
description: Pasos importantes para asegurarse de que la impresión funciona correctamente
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a90d104915ecdd31d9ac35a6393fba74a3816ea8
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826454"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impresión para el escritorio administrado por Microsoft

A medida que esté listo para inscribirse en el escritorio administrado de Microsoft, debe evaluar los requisitos de impresión y determinar el enfoque adecuado para su entorno. Tiene tres opciones:
 
- Implemente la solución de impresión de nube híbrida de Microsoft para que los dispositivos de escritorio administrados por Microsoft puedan detectar fácilmente impresoras. Para obtener más información, vea [deploy Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
- Implemente las impresoras directamente mediante un script de PowerShell personalizado. Siga los pasos de la sección [configurar impresoras locales](#set-up-local-printers) para hacerlo.
- Use una solución de impresión en la nube que no sea de Microsoft que sea compatible con dispositivos Windows 10 que estén Unidos a un dominio de Azure Active Directory. La solución debe cumplir los requisitos de software para el escritorio administrado por Microsoft. Para obtener más información, vea requisitos de la [aplicación de escritorio administrada de Microsoft](../service-description/mmd-app-requirements.md).
 
En todos los casos, si los controladores de impresora no están disponibles en Microsoft Update o en Microsoft Store, tendrá que obtenerlos usted mismo y tenerlos empaquetados para su implementación en dispositivos de escritorio administrados por Microsoft con Microsoft Intune. Para obtener más información, vea [Intune Standalone-Win32 App Management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impresoras locales

Si ha decidido implementar impresoras mediante un script de PowerShell personalizado y ha preparado los recursos de impresión, siga estos pasos para implementar las impresoras compartidas:

1.  Navegue al portal de escritorio administrado por Microsoft.
2.  Envíe una solicitud etiquetada para la implementación de la *impresora* en la sección **support > support** requests del portal de administración, donde se proporcionan los siguientes detalles:
    - Todas las rutas de UNC a ubicaciones de impresoras compartidas que se deben implementar para dispositivos de escritorio administrados por Microsoft
    - Grupos de usuarios que necesitan acceso a estas impresoras compartidas
3.  Mediante el portal de administración, le informaremos cuando se haya completado la solicitud. Inicialmente, solo implementaremos la configuración en los dispositivos del grupo de implementación de prueba.
4.  Debe probar y confirmar si la configuración funciona según lo previsto. Responda mediante la pestaña **discusión** de la solicitud de soporte para informarnos cuando haya completado las pruebas.
5.  A continuación, implementaremos la configuración en los otros grupos de implementación.
