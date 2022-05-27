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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Use los informes DLP de Office 365 para ver el número de coincidencias de directiva DLP, invalidaciones o falsos positivos y ver si están a la alza o a la baja con el tiempo.
ms.openlocfilehash: 01064662e0af82ec98837c8518172bcfeffbaa96
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753548"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Ver los informes de prevención de pérdida de datos

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Después de crear las directivas de prevención de pérdida de datos (DLP) de Microsoft Purview, querrá comprobar que funcionan según lo previsto y ayudarle a mantener la conformidad. Con los informes DLP en el portal de cumplimiento Microsoft Purview, puede ver rápidamente:
  
- **Coincidencias de directiva DLP** En este informe se muestra el recuento de coincidencias de directivas DLP con el tiempo. Puede filtrar el informe por fecha, ubicación, directiva o acción. Puede usar este informe para: 
    
  - Ajuste o perfeccione sus directivas DLP a medida que las ejecuta en modo de prueba. La regla específica que coincide con el contenido.
    
  - Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
    
  - Descubrir los procesos de negocio que infringen las directivas DLP de su organización.
    
  - Vea qué acciones se aplican al contenido para comprender cualquier impacto empresarial de las directivas DLP.
    
  - Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.
    
  - Vea una lista de los usuarios principales y repita los usuarios que contribuyen a los incidentes de su organización.
    
  - Vea una lista de los tipos principales de información confidencial de su organización.
    
- **Incidentes dlp** Este informe también muestra las coincidencias de directivas con el tiempo, como el informe de coincidencias de directivas. Sin embargo, el informe de coincidencias de directivas muestra coincidencias en un nivel de regla; por ejemplo, si un correo electrónico coincidía con tres reglas diferentes, la directiva coincide con el informe que muestra tres elementos de línea diferentes. Por el contrario, el informe de incidentes muestra coincidencias en un nivel de elemento; por ejemplo, si un correo electrónico coincidía con tres reglas diferentes, el informe de incidentes muestra un único elemento de línea para ese fragmento de contenido. 
    
  Dado que los recuentos de informes se agregan de forma diferente, el informe de coincidencias de directivas es mejor para identificar coincidencias con reglas específicas y ajustar las directivas DLP. El informe de incidentes es mejor para identificar partes específicas del contenido que sean problemáticas para las directivas DLP.
    
- **Falsos positivos e invalidaciones de DLP** Si la directiva DLP permite a los usuarios invalidarla o notificar un falso positivo, este informe muestra un recuento de dichas instancias a lo largo del tiempo. Puede filtrar el informe por fecha, ubicación o directiva. Puede usar este informe para: 
    
  - Ajuste o perfeccione sus directivas DLP al ver qué directivas incurren en un gran número de falsos positivos.
    
  - Vea las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de política anulando la política.
    
  - Descubra dónde las políticas de DLP entran en conflicto con los procesos comerciales válidos al incurrir en una gran cantidad de anulaciones de usuarios.
    
Todos los informes de DLP pueden mostrar los datos del período de tiempo de cuatro meses más reciente. Los datos más recientes pueden tardar hasta 24 horas en aparecer en los informes.
  
Puede encontrar estos informes en el **panel** de **informes** \> de portal de cumplimiento Microsoft Purview\>.
  
![La directiva DLP coincide con el informe.](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Visualización de la justificación enviada por un usuario para una invalidación

Si la directiva DLP permite a los usuarios invalidarla, puede usar el informe de falsos positivos e invalidaciones para ver el texto enviado por los usuarios en la sugerencia de directiva.
  
![Campo Justificación en detalles del informe de invalidación y falsos positivos dlp.](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Tomar medidas sobre conclusiones y recomendaciones

Los informes pueden mostrar conclusiones y recomendaciones en las que puede hacer clic en el icono de advertencia rojo para ver detalles sobre posibles problemas y tomar posibles medidas correctivas.
  
![Hacer clic en un icono de información para ver los detalles y las acciones que se van a realizar.](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Permisos para informes DLP

Para ver los informes DLP en el Centro de cumplimiento de seguridad &, debe tener asignado lo siguiente:

- **Rol lector de seguridad** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>. De forma predeterminada, este rol se asigna a los grupos de roles Administración de la organización y Lector de seguridad en el centro de administración de Exchange.

- **Ver solo el rol de administración de cumplimiento DLP** en el Centro de cumplimiento de seguridad &. De forma predeterminada, este rol se asigna a los grupos de roles Administrador de cumplimiento, Administración de la organización, Administrador de seguridad y Lector de seguridad en el Centro de cumplimiento de seguridad &.

- **Rol Destinatarios de solo visualización** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>. De forma predeterminada, este rol se asigna a los grupos de roles Administración de cumplimiento, Administración de la organización y View-Only Administración de la organización en el centro de administración de Exchange.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Búsqueda de los cmdlets para los informes DLP

Para usar la mayoría de los cmdlets para el portal de cumplimiento Microsoft Purview, debe:
  
1. [Conectar a la portal de cumplimiento Microsoft Purview mediante PowerShell remoto](/powershell/exchange/connect-to-scc-powershell)
    
2. Uso de cualquiera de estos [cmdlets del Centro de cumplimiento de seguridad &amp;](/powershell/exchange/exchange-online-powershell)
    
Sin embargo, los informes de DLP necesitan extraer datos de todo Office 365, incluido Exchange Online. Por este motivo, los cmdlets de los informes DLP están disponibles en Exchange Online PowerShell, no en portal de cumplimiento Microsoft Purview PowerShell. Por lo tanto, para usar los cmdlets para los informes de DLP, debe:
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. Use cualquiera de estos cmdlets para los informes de DLP:
    
      - [Get-DlpDetectionsReport](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [Get-DlpDetailReport](/powershell/module/exchange/get-dlpdetailreport)
