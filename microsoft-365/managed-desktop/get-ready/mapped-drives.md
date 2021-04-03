---
title: Preparar unidades asignadas para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de que los usuarios pueden tener acceso a datos en unidades asignadas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f770f5083fe9193660b03e7971b09a127f2dae16
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574564"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparar unidades asignadas para el Escritorio administrado de Microsoft

Muchos entornos empresariales tienen requisitos heredados para las unidades asignadas para permitir que sus usuarios o equipos compartan y almacenen archivos, o para aplicaciones locales. Microsoft no recomienda el uso de unidades asignadas con el Escritorio administrado de Microsoft. En su lugar, se recomienda modernizar las soluciones de acceso a archivos de la siguiente manera:
  
- Migre las unidades asignadas que usan los usuarios individuales a OneDrive para la Empresa. 
- Migre las unidades asignadas que usan los equipos para compartir archivos a SharePoint Online. 
- Modernice o reemplace las aplicaciones que usan recursos compartidos de archivos locales para quitar ese requisito.
  
La modernización de estos servicios permitirá la mejor experiencia de usuario con Microsoft Managed Desktop. Los Servicios de Microsoft FastTrack pueden ayudarle a modernizar su entorno con Servicios en la nube de Microsoft. Puedes comprobar si eres elegible para los servicios FastTrack en [Servicios](/fasttrack/m365-eligible-services-and-plans) y planes elegibles y, a continuación, ponte en contacto con ellos directamente para prepararte para Microsoft Managed Desktop. Para obtener información sobre FastTrack OneDrive para la Empresa o la migración de SharePoint Online, vea [Data Migration](/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unidades asignadas en El escritorio administrado de Microsoft
 
Si no puede quitar o reemplazar unidades asignadas para algunos casos de uso, debe enviar una solicitud de soporte técnico en el portal de administración de Escritorio administrado de Microsoft para que se implementen en usuarios de Escritorio administrado de Microsoft.
    
Para dicha solicitud, tendrá que proporcionar los siguientes detalles en la solicitud de soporte técnico: 

- Todas las rutas UNC a ubicaciones de recurso compartido de archivos que tendrán que asignarse para dispositivos de Escritorio administrado de Microsoft 
- Grupos de usuarios que requieren acceso a estas ubicaciones de recurso compartido de archivos 
- Cualquier letra de unidad específica que necesite asignarse (si es necesario)

Por ejemplo:

| Letra de unidad | Ruta unc | Grupo de usuarios |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Es toda su responsabilidad asegurarse de que los usuarios y grupos tienen y mantienen los permisos adecuados para tener acceso a ubicaciones de recursos compartidos de archivos y que los servicios de archivos locales sigan siendo accesibles. Además, debe quitar los requisitos para dichos recursos compartidos de archivos tan pronto como sea posible.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Para que las unidades asignadas se implementen en Microsoft Managed Desktop
 
Asegúrese de que las unidades asignadas no se pueden evitar y ha revisado cuidadosamente los requisitos antes de enviar cualquier solicitud de servicio. A continuación, siga estos pasos:

1. Vaya a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y seleccione "Solución de problemas + soporte técnico" y busque "Solicitudes de servicio" en la sección Escritorio administrado de Microsoft.  
2. Envíe una solicitud de soporte técnico titulada "Implementación de unidades asignadas" y proporcione todos los detalles de recurso compartido de archivos necesarios.  
3. Las operaciones de TI de Escritorio administrado de Microsoft aconsejarán, mediante actualizaciones de solicitudes de soporte técnico, cuando se haya completado la solicitud. Inicialmente, esta configuración solo se implementará en dispositivos del grupo de implementación de prueba.  
4. Debe probar y confirmar si la configuración implementada por las operaciones de TI de Escritorio administrado de Microsoft funciona como espera. Responda con la pestaña Discusión en los detalles de la misma solicitud de soporte técnico para notificar a las operaciones de TI de Escritorio administrado de Microsoft una vez completadas las pruebas.  
5. A continuación, el equipo de operaciones de TI de Escritorio administrado de Microsoft implementará la configuración en los demás grupos de implementación. 

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar [Requisitos previos de Microsoft Managed Desktop](prerequisites.md).
2. [Usar herramientas de evaluación de preparación](readiness-assessment-tool.md).
3. [Requisitos previos para cuentas de invitados](guest-accounts.md)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft](certs-wifi-lan.md)
6. [Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft](authentication.md)
7. [Aplicaciones en Escritorio administrado de Microsoft](apps.md)
8. [Preparar unidades asignadas para Microsoft Managed Desktop](mapped-drives.md) (este artículo)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md)
