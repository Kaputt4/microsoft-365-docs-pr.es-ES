---
title: Preparar unidades asignadas para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de que los usuarios pueden tener acceso a datos en unidades asignadas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: d8100323350b11cb2329d752892cd64b1bc764a0
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444562"
---
# <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparar unidades asignadas para el Escritorio administrado de Microsoft

Muchos entornos empresariales tienen requisitos heredados para las unidades asignadas para permitir que sus usuarios o equipos compartan y almacenen archivos, o para aplicaciones locales.

Microsoft no recomienda el uso de unidades asignadas con el Escritorio administrado de Microsoft. En su lugar, se recomienda modernizar las soluciones de acceso a archivos de la siguiente manera:
  
- Migre las unidades asignadas que usan los usuarios individuales OneDrive para la Empresa.
- Migre las unidades asignadas que usan los equipos para compartir archivos a SharePoint Online.
- Modernice o reemplace las aplicaciones que usan recursos compartidos de archivos locales para quitar ese requisito.
  
La modernización de estos servicios permitirá la mejor experiencia de usuario con Microsoft Managed Desktop. Microsoft FastTrack Services puede ayudarle a modernizar su entorno con Microsoft Cloud Services. Puedes comprobar si eres elegible para los servicios FastTrack servicios elegibles en [Los planes y servicios elegibles](/fasttrack/m365-eligible-services-and-plans). A continuación, póngase en contacto con ellos directamente para prepararse para Microsoft Managed Desktop. Para obtener más información sobre FastTrack OneDrive para la Empresa o SharePoint online migration, vea [Data Migration](/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unidades asignadas en El escritorio administrado de Microsoft

Si no puede quitar o reemplazar unidades asignadas en algunos casos de uso, debe enviar una solicitud de soporte técnico en el Portal de administración de Escritorio administrado de Microsoft para que se implementen en usuarios de Escritorio administrado de Microsoft.

Para dicha solicitud, debe proporcionar los siguientes detalles en la solicitud de soporte técnico:

- Todas las rutas de acceso UNC a ubicaciones de recurso compartido de archivos que tendrán que asignarse para dispositivos de Escritorio administrado de Microsoft.
- Grupos de usuarios que requieren acceso a estas ubicaciones de recurso compartido de archivos.
- Cualquier letra de unidad específica que necesite asignarse (si es necesario).

Por ejemplo:

| Letra de unidad | Ruta unc | Grupo de usuarios |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Es toda su responsabilidad:

- Asegúrese de que los usuarios y grupos tienen, y mantienen, los permisos adecuados para tener acceso a ubicaciones de recursos compartidos de archivos
- Tener accesibles los servicios de archivos locales.

Debe quitar los requisitos para dichos recursos compartidos de archivos tan pronto como sea posible.

**Para que las unidades asignadas se implementen en Microsoft Managed Desktop:**

Asegúrese de que las unidades asignadas no se pueden evitar y ha revisado cuidadosamente los requisitos antes de enviar cualquier solicitud de soporte técnico.

1. Vaya a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y seleccione **Solución de problemas + compatibilidad**.
1. En la **sección Escritorio administrado de Microsoft** , seleccione **Solicitudes de servicio**.
1. Envíe una solicitud de soporte técnico titulada "Implementación de unidades asignadas" y proporcione todos los detalles de recurso compartido de archivos necesarios.  
1. Las operaciones de TI de Escritorio administrado de Microsoft aconsejarán, mediante actualizaciones de solicitudes de soporte técnico, cuando se haya completado la solicitud. Inicialmente, esta configuración solo se implementará en dispositivos del grupo de implementación de prueba.  
1. Debe probar y confirmar si la configuración implementada por las operaciones de TI de Escritorio administrado de Microsoft funciona como espera.
1. En la misma solicitud de soporte técnico, responda con la **pestaña** Discusión para notificar a las operaciones de TI de Escritorio administrado de Microsoft una vez completadas las pruebas.  
1. A continuación, el equipo de operaciones de TI de Escritorio administrado de Microsoft implementará la configuración en los demás grupos de implementación.

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para El escritorio administrado de Microsoft

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
1. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. Preparar unidades asignadas (en este artículo).
1. [Preparar los recursos de impresión](printing.md).
1. [Nombres del dispositivo](address-device-names.md) de dirección.
