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
ms.openlocfilehash: 01b26ff33e02a1b26e91bb6399a73c9b22a6ba19
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191097"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparar unidades asignadas para el Escritorio administrado de Microsoft

Muchos entornos empresariales tienen requisitos heredados para las unidades asignadas para permitir que sus usuarios o equipos compartan y almacenen archivos, o para aplicaciones locales. Microsoft no recomienda el uso de unidades asignadas con el Escritorio administrado de Microsoft. En su lugar, se recomienda modernizar las soluciones de acceso a archivos de la siguiente manera:
  
- Migre las unidades asignadas que usan los usuarios individuales OneDrive para la Empresa. 
- Migre las unidades asignadas que usan los equipos para compartir archivos a SharePoint Online. 
- Modernice o reemplace las aplicaciones que usan recursos compartidos de archivos locales para quitar ese requisito.
  
La modernización de estos servicios permitirá la mejor experiencia del usuario con Escritorio administrado de Microsoft. Microsoft FastTrack Services puede ayudarle a modernizar su entorno con Microsoft Cloud Services. Puedes comprobar si eres elegible para los servicios FastTrack en [Los](/fasttrack/m365-eligible-services-and-plans) planes y servicios elegibles y, a continuación, ponte en contacto con ellos directamente para prepararte para Escritorio administrado de Microsoft. Para obtener información sobre FastTrack OneDrive para la Empresa o SharePoint online migration, vea [Data Migration](/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unidades asignadas en Escritorio administrado de Microsoft
 
Si no puede quitar o reemplazar unidades asignadas en algunos casos de uso, debe enviar una solicitud de soporte técnico en el portal de administración de Escritorio administrado de Microsoft para que se implementen en Escritorio administrado de Microsoft usuarios.
    
Para dicha solicitud, tendrá que proporcionar los siguientes detalles en la solicitud de soporte técnico: 

- Todas las rutas DE ACCESO UNC a ubicaciones de recurso compartido de archivos que tendrán que asignarse para Escritorio administrado de Microsoft dispositivos 
- Grupos de usuarios que requieren acceso a estas ubicaciones de recurso compartido de archivos 
- Cualquier letra de unidad específica que necesite asignarse (si es necesario)

Por ejemplo:

| Letra de unidad | Ruta unc | Grupo de usuarios |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Es toda su responsabilidad asegurarse de que los usuarios y grupos tienen y mantienen los permisos adecuados para tener acceso a ubicaciones de recursos compartidos de archivos y que los servicios de archivos locales sigan siendo accesibles. Además, debe quitar los requisitos para dichos recursos compartidos de archivos tan pronto como sea posible.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Para que las unidades asignadas se implementen en Escritorio administrado de Microsoft
 
Asegúrese de que las unidades asignadas no se pueden evitar y ha revisado cuidadosamente los requisitos antes de enviar cualquier solicitud de servicio. A continuación, siga estos pasos:

1. Vaya a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y seleccione "Solución de problemas + soporte técnico" y busque "Solicitudes de servicio" en la sección Escritorio administrado de Microsoft servicio.  
2. Envíe una solicitud de soporte técnico titulada "Implementación de unidades asignadas" y proporcione todos los detalles de recurso compartido de archivos necesarios.  
3. Escritorio administrado de Microsoft Las operaciones de TI aconsejarán, mediante el uso de actualizaciones de solicitudes de soporte técnico, cuando se haya completado la solicitud. Inicialmente, esta configuración solo se implementará en dispositivos del grupo de implementación de prueba.  
4. Debe probar y confirmar si la configuración implementada por el Escritorio administrado de Microsoft operaciones de TI funciona como espera. Responda con la pestaña Discusión en los detalles de la misma solicitud de soporte técnico para notificar a Escritorio administrado de Microsoft operaciones de TI una vez completadas las pruebas.  
5. Escritorio administrado de Microsoft A continuación, el equipo de operaciones de TI implementará la configuración en los otros grupos de implementación. 

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para Escritorio administrado de Microsoft

1. Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)
2. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. Preparar unidades asignadas (en este artículo).
1. [Preparar los recursos de impresión](printing.md).
1. [Nombres del dispositivo](address-device-names.md) de dirección.