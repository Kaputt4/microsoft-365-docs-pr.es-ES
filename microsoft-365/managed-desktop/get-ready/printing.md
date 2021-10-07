---
title: Preparar recursos de impresión para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de que la impresión funciona sin problemas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 81de89a704c8ff8717439d83e70504ba2fe8e410
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188918"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impresión para el Escritorio administrado de Microsoft

A medida que esté listo para inscribirse en Escritorio administrado de Microsoft, debe evaluar los requisitos de impresión y determinar el enfoque adecuado para su entorno. Tiene tres opciones:

- Implemente la solución de impresión universal de Microsoft para que sea Escritorio administrado de Microsoft dispositivos detectar impresoras. Para obtener más información, vea [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).
- Implemente impresoras directamente mediante un script de PowerShell personalizado. Siga los pasos de la [sección Configurar impresoras](#set-up-local-printers) locales.
- Use una solución de impresión en la nube que no sea de Microsoft que sea compatible con Windows 10 dispositivos unidos a un dominio Azure Active Directory usuario. La solución debe cumplir los requisitos de software para Escritorio administrado de Microsoft. Para obtener más información, [Escritorio administrado de Microsoft requisitos de la aplicación](../service-description/mmd-app-requirements.md).
 
En todos los casos, si los controladores de impresora no están disponibles en Microsoft Update o en el Microsoft Store, tendrás que obtenerlos tú mismo y empaquetarlos para su implementación en los dispositivos Escritorio administrado de Microsoft con Microsoft Intune. Para obtener más información, [consulta Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impresoras locales

Si ha decidido implementar impresoras mediante un script de PowerShell personalizado y ha preparado los recursos de impresión, siga estos pasos para que las impresoras compartidas se implementen:

1. Vaya al portal de Escritorio administrado de Microsoft web.
2. Envíe una solicitud con la etiqueta *Implementación* de impresora en la sección Solicitudes de soporte **> soporte** técnico del Portal de administración, proporcionando estos detalles:
    - Todas las rutas unc a las ubicaciones de impresora compartidas que se deben implementar para Escritorio administrado de Microsoft dispositivos
    - Grupos de usuarios que requieren acceso a estas impresoras compartidas
3. Con el Portal de administración, le haremos saber cuándo se ha completado la solicitud. Inicialmente, solo implementaremos la configuración en los dispositivos del grupo de implementación de prueba.
4. Debe probar y confirmar si la configuración funciona como espera. Responda mediante la pestaña **Discusión** de la solicitud de soporte técnico para que sepamos cuándo ha completado las pruebas.
5. A continuación, implementaremos la configuración en los otros grupos de implementación.

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
2. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. [Preparar las unidades asignadas](mapped-drives.md).
1. Preparar los recursos de impresión (en este artículo).
1. [Nombres del dispositivo](address-device-names.md) de dirección.
