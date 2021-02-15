---
title: Preparar unidades asignadas para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse de
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 34b2186ea3f9129ae7bb602aee879d7d23424136
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841069"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparar unidades asignadas para el Escritorio administrado de Microsoft

Muchos entornos empresariales tienen requisitos heredados para las unidades asignadas para permitir que sus usuarios o equipos compartan y almacenen archivos, o para aplicaciones locales. Microsoft no recomienda el uso de unidades asignadas con el Escritorio administrado de Microsoft. En su lugar, se recomienda modernizar las soluciones de acceso a archivos de la siguiente manera:
  
- Migrar unidades asignadas usadas por usuarios individuales a OneDrive para la Empresa. 
- Migrar unidades asignadas que usan los equipos para compartir archivos a SharePoint Online. 
- Modernice o reemplace las aplicaciones que usen recursos compartidos de archivos locales para quitar ese requisito.
  
La modernización de estos servicios permitirá la mejor experiencia de usuario con escritorio administrado de Microsoft. Los Servicios de Microsoft FastTrack pueden ayudarle a modernizar su entorno mediante servicios en la nube de Microsoft. Puede comprobar si es apto para los [](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) servicios de FastTrack en Los Servicios y Planes elegibles y, a continuación, ponerse en contacto con ellos directamente para prepararse para el Escritorio administrado de Microsoft. Para obtener información general sobre la migración de OneDrive para la Empresa o SharePoint Online de FastTrack, vea [Migración de datos.](https://docs.microsoft.com/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unidades asignadas en escritorio administrado de Microsoft
 
Si no puede quitar o reemplazar unidades asignadas para algunos casos de uso, debe enviar una solicitud de soporte técnico en el portal de administración de Escritorio administrado de Microsoft para que se implementen en usuarios de Escritorio administrado de Microsoft.
    
Para esta solicitud, tendrá que proporcionar los siguientes detalles en la solicitud de soporte técnico: 

- Todas las rutas de acceso UNC a ubicaciones de recurso compartido de archivos que deban asignarse para dispositivos de Escritorio administrado de Microsoft 
- Grupos de usuarios que requieren acceso a estas ubicaciones de recursos compartidos de archivos 
- Cualquier letra de unidad específica que deba asignarse (si es necesario)

Por ejemplo:

| Letra de unidad | Ruta de acceso UNC | Grupo de usuarios |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Es toda su responsabilidad asegurarse de que los usuarios y grupos tengan y mantengan los permisos adecuados para tener acceso a las ubicaciones de recursos compartidos de archivos y que los servicios de archivos locales sigan siendo accesibles. Además, debe quitar los requisitos para dichos recursos compartidos de archivos tan pronto como sea posible.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Para tener unidades asignadas implementadas en el Escritorio administrado de Microsoft
 
Asegúrese de que las unidades asignadas no se pueden evitar y ha revisado cuidadosamente los requisitos antes de enviar cualquier solicitud de servicio. A continuación, siga estos pasos:

1. Ve a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y selecciona "Solución de problemas y soporte técnico" y busca "Solicitudes de servicio" en la sección Escritorio administrado de Microsoft.  
2. Envía una solicitud de soporte técnico titulada "Implementación de unidades asignadas" y proporciona todos los detalles necesarios del recurso compartido de archivos.  
3. Las operaciones de TI de escritorio administrado de Microsoft informarán, mediante el uso de actualizaciones de solicitudes de soporte técnico, cuando se haya completado la solicitud. Inicialmente, esta configuración solo se implementará en los dispositivos del grupo de implementación de prueba.  
4. Debe probar y confirmar si la configuración implementada por las operaciones de TI de Escritorio administrado de Microsoft funciona según lo esperado. Responda con la pestaña Discusión en los detalles de la misma solicitud de soporte técnico para notificar a las operaciones de TI de Escritorio administrado de Microsoft una vez que haya completado las pruebas.  
5. A continuación, el equipo de operaciones de TI de Escritorio administrado de Microsoft implementará la configuración en los demás grupos de implementación. 
