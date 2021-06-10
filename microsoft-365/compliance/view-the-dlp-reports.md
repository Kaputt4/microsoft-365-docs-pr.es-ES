---
title: Ver los informes de prevención de pérdida de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Use los informes DLP de Office 365 para ver el número de coincidencias de directivas DLP, invalidaciones o falsos positivos y ver si van hacia arriba o hacia abajo con el tiempo.
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928394"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Ver los informes de prevención de pérdida de datos

Después de crear las directivas de prevención de pérdida de datos (DLP), querrá comprobar que funcionan según lo previsto y le ayudarán a cumplir las normas. Con los informes DLP en el Centro de &amp; cumplimiento de seguridad, puede ver rápidamente:
  
- **Coincidencias de directiva DLP** Este informe muestra el recuento de coincidencias de directivas DLP con el tiempo. Puede filtrar el informe por fecha, ubicación, directiva o acción. Puede usar este informe para: 
    
  - Ajuste o perfeccione sus directivas DLP a medida que las ejecuta en modo de prueba. La regla específica que coincide con el contenido.
    
  - Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
    
  - Descubrir los procesos de negocio que infringen las directivas DLP de su organización.
    
  - Vea qué acciones se aplican al contenido para comprender cualquier impacto empresarial de las directivas DLP.
    
  - Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.
    
  - Vea una lista de los usuarios principales y repita los usuarios que contribuyen a los incidentes de su organización.
    
  - Vea una lista de los tipos principales de información confidencial de su organización.
    
- **Incidentes dlp** Este informe también muestra coincidencias de directiva con el tiempo, como el informe de coincidencias de directiva. Sin embargo, el informe de coincidencias de directiva muestra coincidencias en un nivel de regla; por ejemplo, si un correo electrónico coincide con tres reglas diferentes, el informe de coincidencias de directiva muestra tres elementos de línea diferentes. En cambio, el informe de incidentes muestra coincidencias en un nivel de elemento; por ejemplo, si un correo electrónico coincide con tres reglas diferentes, el informe de incidentes muestra un único elemento de línea para ese fragmento de contenido. 
    
  Dado que los recuentos de informes se agregan de forma diferente, el informe de coincidencias de directivas es mejor para identificar coincidencias con reglas específicas y ajustar directivas DLP. El informe de incidentes es mejor para identificar partes específicas del contenido que sean problemáticas para las directivas DLP.
    
- **Falsos positivos e invalidaciones de DLP** Si la directiva DLP permite a los usuarios invalidarla o notificar un falso positivo, este informe muestra un recuento de dichas instancias con el tiempo. Puede filtrar el informe por fecha, ubicación o directiva. Puede usar este informe para: 
    
  - Ajuste o perfeccione sus directivas DLP al ver qué directivas incurren en un gran número de falsos positivos.
    
  - Vea las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de política anulando la política.
    
  - Descubra dónde las políticas de DLP entran en conflicto con los procesos comerciales válidos al incurrir en una gran cantidad de anulaciones de usuarios.
    
Todos los informes de DLP pueden mostrar los datos del período de tiempo de cuatro meses más reciente. Los datos más recientes pueden tardar hasta 24 horas en aparecer en los informes.
  
Puede encontrar estos informes en el Panel de informes del &amp; Centro de seguridad y \>  \> **cumplimiento.**
  
![Informe de coincidencias de directivas DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Ver la justificación enviada por un usuario para una invalidación

Si la directiva DLP permite a los usuarios invalidarla, puede usar el informe de falsos positivos e invalidaciones para ver el texto enviado por los usuarios en la sugerencia de directiva.
  
![Campo De justificación en los detalles del informe de falso positivo e invalidación de DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Tomar medidas sobre información y recomendaciones

Los informes pueden mostrar información y recomendaciones en las que puede hacer clic en el icono rojo de advertencia para ver detalles sobre posibles problemas y realizar posibles acciones correctivas.
  
![Hacer clic en un icono de información para ver los detalles y las acciones que se deben realizar](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Permisos para informes DLP

Para ver los informes DLP en el Centro de seguridad & cumplimiento, debe tener asignado lo siguiente:

- **Rol lector de** seguridad en el centro Exchange administración. De forma predeterminada, este rol se asigna a los grupos de roles Administración de la organización y Lector de seguridad en el centro Exchange administración.

- **Rol Administración de cumplimiento DLP de solo** vista en el Centro de seguridad & cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles Administrador de cumplimiento, Administración de la organización, Administrador de seguridad y Lector de seguridad en el Centro de seguridad & cumplimiento.

- **Rol Destinatarios de solo vista** en el centro Exchange administración. De forma predeterminada, este rol se asigna a los grupos de roles Administración de cumplimiento, Administración de la organización y administración de View-Only en el centro de administración de Exchange cumplimiento.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Buscar los cmdlets de los informes DLP

Para usar la mayoría de los cmdlets para el Centro de seguridad y cumplimiento, necesita:
  
1. [Conectar al Centro de cumplimiento &amp; de seguridad con PowerShell remoto](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. Use cualquiera de estos [ &amp; cmdlets del Centro de seguridad y cumplimiento](/powershell/exchange/exchange-online-powershell)
    
Sin embargo, los informes de DLP necesitan extraer datos de todo Office 365, incluido Exchange Online. Por este motivo, los cmdlets de los informes DLP están disponibles en Exchange Online Powershell, no en &amp; Powershell del Centro de seguridad y cumplimiento. Por lo tanto, para usar los cmdlets para los informes de DLP, debe:
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. Use cualquiera de estos cmdlets para los informes de DLP:
    
      - [Get-DlpDetectionsReport](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [Get-DlpDetailReport](/powershell/module/exchange/get-dlpdetailreport)
