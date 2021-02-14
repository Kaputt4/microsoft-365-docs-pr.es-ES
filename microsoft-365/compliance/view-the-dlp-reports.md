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
description: Use los informes DLP de Office 365 para ver el número de coincidencias de directivas DLP, invalidaciones o falsos positivos y ver si son tendencias ascendentes o descendentes con el tiempo.
ms.openlocfilehash: 1ddcd60dc9314779ade2f7ceae02d336f902e483
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819000"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Ver los informes de prevención de pérdida de datos

Después de crear las directivas de prevención de pérdida de datos (DLP), es posible que desee comprobar que funcionen según lo previsto y le ayudarán a cumplir las normativas. Con los informes DLP en el Centro de &amp; cumplimiento de seguridad, puede ver rápidamente:
  
- **Coincidencias de directiva DLP** Este informe muestra el recuento de coincidencias de directivas DLP con el tiempo. Puede filtrar el informe por fecha, ubicación, directiva o acción. Puede usar este informe para: 
    
  - Ajuste o refine las directivas DLP a medida que las ejecuta en modo de prueba. Puede ver la regla específica que coincidió con el contenido.
    
  - Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
    
  - Descubrir los procesos de negocio que infringen las directivas DLP de su organización.
    
  - Comprenda el impacto empresarial de las directivas DLP al ver qué acciones se aplican al contenido.
    
  - Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.
    
  - Vea una lista de los principales usuarios y repita los usuarios que contribuyen a los incidentes de su organización.
    
  - Vea una lista de los tipos principales de información confidencial de su organización.
    
- **Incidentes de DLP** Este informe también muestra coincidencias de directiva con el tiempo, como el informe de coincidencias de directiva. Sin embargo, el informe de coincidencias de directiva muestra coincidencias en un nivel de regla; por ejemplo, si un correo electrónico coincide con tres reglas diferentes, el informe de coincidencias de directiva muestra tres elementos de línea diferentes. Por el contrario, el informe de incidentes muestra coincidencias en un nivel de elemento; por ejemplo, si un correo electrónico coincide con tres reglas diferentes, el informe de incidentes muestra un único elemento de línea para ese elemento de contenido. 
    
  Dado que los recuentos de informes se agregan de forma diferente, el informe de coincidencias de directivas es mejor para identificar coincidencias con reglas específicas y ajustar directivas DLP. El informe de incidentes es mejor para identificar partes específicas de contenido que son problemáticas para las directivas DLP.
    
- **Falsos positivos e invalidaciones de DLP** Si la directiva DLP permite a los usuarios invalidarla o notificar un falso positivo, este informe muestra un recuento de esas instancias a lo largo del tiempo. Puede filtrar el informe por fecha, ubicación o directiva. Puede usar este informe para: 
    
  - Ajuste o refine las directivas DLP al ver qué directivas incurren en un gran número de falsos positivos.
    
  - Vea las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva invalidando la directiva.
    
  - Descubra dónde están en conflicto las directivas DLP con procesos de negocio válidos al incurrir en un gran número de invalidaciones de usuario.
    
Todos los informes DLP pueden mostrar datos del período de cuatro meses más reciente. Los datos más recientes pueden tardar hasta 24 horas en aparecer en los informes.
  
Puede encontrar estos informes en el Panel de informes &amp; del Centro de cumplimiento \> **de** \> **seguridad.**
  
![Informe de coincidencias de directiva DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Ver la justificación enviada por un usuario para una invalidación

Si la directiva DLP permite a los usuarios invalidarla, puede usar el informe de falsos positivos e invalidación para ver el texto enviado por los usuarios en la sugerencia de directiva.
  
![Campo de justificación en los detalles del informe de falso positivo e invalidación de DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Tomar medidas sobre perspectivas y recomendaciones

Los informes pueden mostrar información y recomendaciones donde puede hacer clic en el icono de advertencia roja para ver detalles sobre posibles problemas y tomar posibles medidas correctivas.
  
![Hacer clic en un icono de información para ver los detalles y las acciones que se deben realizar](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Permisos para informes DLP

Para ver informes DLP en el Centro de & cumplimiento, debe tener asignado lo siguiente:

- **Rol Lector de** seguridad en el Centro de administración de Exchange. De forma predeterminada, este rol se asigna a los grupos de roles Administración de la organización y Lector de seguridad en el Centro de administración de Exchange.

- **Rol Administración de cumplimiento DLP de solo** vista en el Centro de & cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles Administrador de cumplimiento, Administración de la organización, Administrador de seguridad y Lector de seguridad en el Centro de & Cumplimiento.

- **Rol Destinatarios de solo vista** en el Centro de administración de Exchange. De forma predeterminada, este rol se asigna a los grupos de roles Administración de cumplimiento, Administración de la organización y Administración View-Only organización en el Centro de administración de Exchange.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Buscar los cmdlets para los informes DLP

Para usar la mayoría de los cmdlets para el Centro de seguridad y cumplimiento, necesita:
  
1. [Conectarse al Centro de &amp; cumplimiento de seguridad con PowerShell remoto](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Usar cualquiera de estos [ &amp; cmdlets del Centro de cumplimiento de seguridad](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
Sin embargo, los informes de DLP necesitan extraer datos de todo Office 365, incluido Exchange Online. Por este motivo, los cmdlets de los informes DLP están disponibles en Exchange Online Powershell, no en powershell del Centro de &amp; cumplimiento de seguridad. Por lo tanto, para usar los cmdlets para los informes de DLP, debe:
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Use cualquiera de estos cmdlets para los informes de DLP:
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

