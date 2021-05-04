---
title: Solución de problemas de suspensión de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Solucionar errores relacionados con las retenciones legales aplicadas a custodios y orígenes de datos no custodiados en eDiscovery principal.
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860391"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>Solución de problemas de suspensión de eDiscovery

En este artículo se analizan los problemas comunes que pueden producirse con las retenciones de exhibición de documentos electrónicos y cómo resolverlos. El artículo también incluye prácticas recomendadas para ayudarle a mitigar o evitar estos problemas.

## <a name="recommended-practices"></a>Procedimientos recomendados

Para reducir el número de errores relacionados con las retenciones de exhibición de documentos electrónicos, se recomiendan los siguientes procedimientos:

- Si una distribución de retención aún está pendiente, con un estado de o , espere hasta que se complete la distribución de retención antes de `On (Pending)` `Off (Pending)` realizar más actualizaciones.

- Combina las actualizaciones en una retención de exhibición de documentos electrónicos en una única solicitud masiva en lugar de actualizar la directiva de retención repetidamente para cada transacción. Por ejemplo, para agregar varios buzones de usuario a una directiva de retención existente mediante el cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) ejecute el comando (o agregue como un bloque de código a un script) para que se ejecute solo una vez para agregar varios usuarios.

  **Correcto:**

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **Incorrecto:**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   En el ejemplo incorrecto anterior, el cmdlet se ejecuta cinco veces distintas para completar la tarea. Para obtener más información acerca de los procedimientos recomendados para agregar usuarios a una directiva de retención, vea la [sección Más](#more-information) información.

- Antes de ponerse en contacto con el Soporte técnico de Microsoft sobre problemas de retención de exhibición de documentos electrónicos, siga los pasos de la sección [Error/problema:](#errorissue-holds-dont-sync) las retenciones no se sincronizan para reintentar la distribución de retención. Este proceso suele resolver problemas temporales, incluidos los errores internos del servidor.

## <a name="errorissue-holds-dont-sync"></a>Error o problema: las retenciones no se sincronizan

Si ve uno de los siguientes mensajes de error al poner a los custodios y orígenes de datos en espera, siga los pasos de resolución para solucionar el problema.

> Recursos: tarda más de lo esperado en implementar la directiva. Podría tardar 2 horas adicionales en actualizar el estado de implementación final, por lo que vuelve a comprobarlo en un par de horas.

> La directiva no se puede implementar en el origen de contenido debido a un problema Office 365 centro de datos. La directiva actual no se aplica a ningún contenido del origen, por lo que no hay ningún impacto de la implementación bloqueada. Para solucionar este problema, intente volver a implementar la directiva.

> Lo sentimos, no pudimos realizar los cambios solicitados en la directiva debido a un error transitorio del servidor interno. Vuelva a intentarlo en 30 minutos.

### <a name="resolution"></a>Solución

1. Conectar [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) de seguridad y cumplimiento y ejecute el siguiente comando para una retención de exhibición de documentos electrónicos:

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. Examine el valor del parámetro *DistributionDetail.* Busque errores como los siguientes:

   > Error: Recursos: tarda más de lo esperado en implementar la directiva. Podría tardar 2 horas adicionales en actualizar el estado de implementación final, por lo que vuelve a comprobarlo en un par de horas.

3. Intente ejecutar el **comando Set-CaseHoldPolicy -RetryDistribution** en la directiva de retención en cuestión; por ejemplo:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a>Más información

- Las instrucciones sobre cómo actualizar directivas de retención para varios usuarios en la sección "Prácticas recomendadas" se deben al hecho de que el sistema bloquea las actualizaciones simultáneas de una directiva de retención. Esto significa que cuando se aplica una directiva de retención actualizada a nuevas ubicaciones de contenido y la directiva de retención está en un estado pendiente, no se pueden agregar ubicaciones de contenido adicionales a la directiva de retención. Estas son algunas cosas que debe tener en cuenta para ayudarle a mitigar este problema:
  
  - Cada vez que se actualiza una retención, pasa inmediatamente a un estado pendiente. El estado pendiente significa que la retención se aplica a las ubicaciones de contenido.
  
  - Si tiene un script que ejecuta un bucle y agrega ubicaciones a la directiva uno a uno (similar al ejemplo incorrecto que se muestra en la sección "Prácticas recomendadas"), la primera ubicación de contenido (por ejemplo, un buzón de usuario) inicia el proceso de sincronización que desencadena el estado pendiente. Esto significa que los demás usuarios que se agregan a la directiva en bucles posteriores producirán un error.
  
  - Si su organización usa un script que ejecuta un bucle para actualizar las ubicaciones de contenido de una directiva de retención, debe actualizar el script para que actualice las ubicaciones en una sola operación masiva (como se muestra en el ejemplo correcto en la sección "Prácticas recomendadas").
