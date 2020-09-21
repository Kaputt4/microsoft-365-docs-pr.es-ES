---
title: Preparar unidades asignadas para el Escritorio administrado de Microsoft
description: Pasos importantes para asegurarse
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: fc216adadea8dd774901d42a754fb288412318a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104599"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparar unidades asignadas para el Escritorio administrado de Microsoft

Muchos entornos empresariales tienen requisitos heredados para las unidades asignadas para permitir que sus usuarios o equipos compartan y almacenen archivos, o para las aplicaciones locales. Microsoft no recomienda el uso de unidades asignadas con el escritorio administrado de Microsoft. En su lugar, se recomienda modernizar las soluciones de acceso a archivos de la siguiente manera:
  
- Migre las unidades asignadas que usan los usuarios individuales a OneDrive para la empresa. 
- Migre las unidades asignadas que usa Teams para compartir archivos en SharePoint Online. 
- Modernice o reemplace todas las aplicaciones que usan recursos compartidos de archivos locales para quitar ese requisito.
  
La modernización de estos servicios permitirá la mejor experiencia de usuario con el escritorio administrado por Microsoft. Los servicios de Microsoft FastTrack le pueden ayudar a modernizar su entorno con los servicios en la nube de Microsoft. Puede comprobar si es elegible para los servicios de FastTrack en los [servicios y planes elegibles](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) y, a continuación, póngase en contacto con ellos directamente para prepararse para el escritorio administrado por Microsoft. Para obtener información sobre la migración de OneDrive para la empresa o de SharePoint Online de FastTrack, consulte [migración de datos](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unidades asignadas en el escritorio administrado por Microsoft
 
Si no puede quitar ni reemplazar las unidades asignadas en algunos casos de uso, debe enviar una solicitud de soporte técnico en el portal de administración de escritorio administrado de Microsoft para que se implementen en los usuarios de escritorio administrados por Microsoft.
    
Para dicha solicitud, deberá proporcionar los siguientes detalles en la solicitud de soporte técnico: 

- Todas las rutas de acceso UNC a ubicaciones de recursos compartidos de archivos que se deben asignar a los dispositivos de escritorio administrados por Microsoft 
- Grupos de usuarios que necesitan acceso a estas ubicaciones de recursos compartidos de archivos 
- Cualquier letra de unidad específica que deba asignarse (si es necesario)

Por ejemplo:

| Letra de unidad | Ruta de acceso UNC | Grupo de usuarios |
|--------------|----------|------------|
| Días  | \\\server\share\Marketing | ContosoMarketing |

Es totalmente responsable de garantizar que los usuarios y grupos tengan y mantenga los permisos adecuados para acceder a las ubicaciones de recursos compartidos de archivos y que los servicios de archivos locales sigan siendo accesibles. Además, debe quitar los requisitos de estos recursos compartidos de archivos lo antes posible.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Para que las unidades asignadas se hayan implementado en el escritorio administrado de Microsoft
 
Asegúrese de que no se pueden evitar las unidades asignadas y de que ha revisado atentamente los requisitos antes de enviar cualquier solicitud de servicio. A continuación, siga estos pasos:

1. Navegue a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y seleccione "solución de problemas + Soporte técnico" y, a continuación, busque "solicitudes de servicio" en la sección Deskop administrados de Microsoft.  
2. Envíe una solicitud de soporte titulada "implementación de unidades asignadas" y proporcione todos los detalles necesarios del recurso compartido de archivos.  
3. Las operaciones de TI de escritorio administradas de Microsoft le avisarán, mediante actualizaciones de solicitudes de soporte, cuando se haya completado la solicitud. Inicialmente, esta configuración solo se implementará en los dispositivos del grupo de implementación de prueba.  
4. Debe probar y confirmar si la configuración implementada por las operaciones de TI de escritorio administradas de Microsoft funciona según lo previsto. Responda mediante la pestaña discusión en los detalles de la misma solicitud de soporte técnico para notificar a las operaciones de TI de escritorio administradas de Microsoft una vez que haya completado las pruebas.  
5. El equipo de operaciones de TI de escritorio administrado de Microsoft implementará la configuración en los demás grupos de implementación. 
