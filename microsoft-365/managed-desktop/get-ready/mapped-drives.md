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
  
- Migre las unidades asignadas que usan los usuarios individuales OneDrive para la Empresa. 
- Migre las unidades asignadas que usan los equipos para compartir archivos a SharePoint Online. 
- Modernice o reemplace las aplicaciones que usan recursos compartidos de archivos locales para quitar ese requisito.
  
La modernización de estos servicios permitirá la mejor experiencia del usuario con Escritorio administrado de Microsoft. Los Servicios de Microsoft FastTrack pueden ayudarle a modernizar su entorno con Servicios en la nube de Microsoft. Puedes comprobar si eres elegible para los servicios de FastTrack en [Servicios](/fasttrack/m365-eligible-services-and-plans) y Planes elegibles y, a continuación, ponte en contacto con ellos directamente para prepararte para Escritorio administrado de Microsoft. Para obtener información general sobre fasttrack OneDrive para la Empresa o SharePoint online migration, vea [Data Migration](/fasttrack/o365-data-migration).

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

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar [Requisitos previos para Escritorio administrado de Microsoft](prerequisites.md).
2. [Usar herramientas de evaluación de preparación](readiness-assessment-tool.md).
3. [Requisitos previos para las cuentas de invitado](guest-accounts.md)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft](certs-wifi-lan.md)
6. [Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft](authentication.md)
7. [Aplicaciones en el Escritorio administrado de Microsoft](apps.md)
8. [Preparar unidades asignadas para Escritorio administrado de Microsoft](mapped-drives.md) (este artículo)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md)
