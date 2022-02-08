---
title: Preparar recursos de impresión para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de que la impresión funciona sin problemas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: a66075637a15eb39eda38e318070af2bcbdc8fe6
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444526"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impresión para el Escritorio administrado de Microsoft

A medida que esté listo para inscribirse en Microsoft Managed Desktop, debe evaluar los requisitos de impresión y determinar el enfoque adecuado para su entorno. Tiene tres opciones:

| Opción | Descripción |
| ------ | ------ |
| Implementar la solución de impresión universal de Microsoft | La solución de impresión universal de Microsoft para facilitar que los dispositivos de Escritorio administrado de Microsoft detecte impresoras. Para obtener más información, vea [What is Universal Print](/universal-print/fundamentals/universal-print-whatis). |
| Implementar impresoras directamente mediante un script de PowerShell personalizado | Siga los pasos de la [sección Configurar impresoras](#set-up-local-printers) locales. |
| Usar una solución de impresión en la nube que no es microsoft | Use una solución de impresión en la nube que no sea de Microsoft que sea compatible con Windows 10 dispositivos y se una a un dominio Azure Active Directory usuario. La solución debe cumplir los requisitos de software para Microsoft Managed Desktop. Para obtener más información, consulta [Requisitos de aplicaciones de Escritorio administrado de Microsoft](../service-description/mmd-app-requirements.md). |

En todas las opciones anteriores, si los controladores de impresora no están disponibles en Microsoft Update o en el Microsoft Store, debe obtenerlos usted mismo y empaquetarlos para su implementación en los dispositivos de Escritorio administrado de Microsoft con Microsoft Intune. Para obtener más información, [consulta Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impresoras locales

En las instrucciones siguientes se supone que ha preparado los recursos de impresión y ha decidido implementar impresoras con un script de PowerShell personalizado.

**Para implementar impresoras con un script de PowerShell personalizado:**

1. Vaya al portal de Escritorio administrado de Microsoft.
1. Envíe una solicitud con la etiqueta *Implementación* de impresora en la sección **Solicitudes > soporte** técnico del Portal de administración.
1. Proporcione los siguientes detalles:
    - Todas las rutas de acceso UNC a ubicaciones de impresora compartidas que tendrán que implementarse para dispositivos de Escritorio administrado de Microsoft.
    - Grupos de usuarios que requieren acceso a estas impresoras compartidas.
1. Con el Portal de administración, le haremos saber cuándo se ha completado la solicitud. Inicialmente, solo implementaremos la configuración en los dispositivos del grupo de implementación de prueba.
1. Pruebe y confirme si la configuración funciona como espera.
1. Responda mediante la **pestaña Discusión** de la solicitud de soporte técnico para que sepamos cuándo ha completado las pruebas.
1. A continuación, implementaremos la configuración en los otros grupos de implementación.

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
1. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. [Preparar las unidades asignadas](mapped-drives.md).
1. Preparar los recursos de impresión (en este artículo).
1. [Nombres del dispositivo](address-device-names.md) de dirección.
