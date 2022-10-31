---
title: Introducción al escáner local de prevención de pérdida de datos
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: En este artículo se describen los requisitos previos y la configuración del analizador local de prevención de pérdida de datos de Microsoft Purview.
ms.openlocfilehash: 8e98f982ed98fa988c87039d962cb4f6312e2146
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68794080"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner"></a>Introducción al examinador de prevención de pérdida de datos en el entorno local

Este artículo le guiará por los requisitos previos y la configuración del escáner local de prevención de pérdidas de datos de Microsoft Purview.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Antes de empezar con el examinador de DLP local, debe confirmar su [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento. La cuenta de administrador que configura las reglas de DLP debe tener asignada una de las siguientes licencias:

- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Gobernanza y protección de la información de Microsoft 365 E5 


Para más información sobre las licencias, vea: [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

> [!IMPORTANT]
> Todos los usuarios que contribuyen a la ubicación examinada agregando archivos o consumiendo archivos deben tener una licencia, no solo el usuario del analizador.

### <a name="permissions"></a>Permisos

Los datos del examinador DLP en el entorno local se pueden ver en el [Explorador de actividades](data-classification-activity-explorer.md). Hay cuatro roles que conceden permisos al explorador de actividad; la cuenta que use para acceder a los datos debe pertenecer a uno de ellos.

- Administrador global
- Administrador de cumplimiento
- Administrador de seguridad
- Administrador de datos de cumplimiento

#### <a name="roles-and-role-groups"></a>Roles y grupos de roles

Hay roles y grupos de roles en la versión preliminar que puede probar para ajustar los controles de acceso.

Esta es una lista de los roles aplicables que se encuentran en versión preliminar. Para obtener más información sobre ellos, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

- Administrador de Information Protection
- Analista de Information Protection
- Investigador de protección de información
- Lector de protección de información

Esta es una lista de los grupos de roles aplicables que se encuentran en versión preliminar. Para obtener más información sobre, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

- Protección de la información
- Administradores de Information Protection
- Analistas de Information Protection
- Investigadores de Information Protection
- Lectores de Information Protection

### <a name="dlp-on-premises-scanner-prerequisites"></a>Requisitos previos del examinador de DLP en el entorno local

- The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.
- Deploy the AIP  client and scanner. For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).
- Debe haber al menos una etiqueta y una directiva publicadas en el espacio empresarial, incluso si todas sus reglas de detección se basan únicamente en tipos de información confidenciales.

## <a name="deploy-the-dlp-on-premises-scanner"></a>Implementar el examinador local de DLP

1. Siga los procedimientos descritos en [Instalar el cliente de etiquetas unificado de AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app). 
2. Siga los procedimientos descritos en [Configurar e instalar el examinador de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install) para completar la instalación del examinador.
    1. La configuración de los trabajos de detección de red es un paso opcional. Puede omitirlo y definir repositorios específicos que se examinarán en su trabajo de examen de contenido.
    2. Debe crear un trabajo de examen de contenido y especificar los repositorios que alojan archivos que deben ser evaluados por el motor de DLP.
    3. Habilite las reglas de DLP en el trabajo de examen de contenido creado y establezca la opción **Aplicar** en **Desactivar**, a menos que desee avanzar directamente a la fase de aplicación de DLP.
3. Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes.

4. Conéctese a la [Extensión de Azure Information Protection en Azure Portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) y agregue sus repositorios al trabajo de examen de contenido que realizará el examen.

5. Realice una de las siguientes acciones para ejecutar su examen:
    1. establezca la programación del examinador
    1. use la opción de **Examinar ahora** en el portal
    1. o ejecutar **Start-AIPScan** cmdlet de PowerShell

   > [!IMPORTANT]
   > Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan. Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.

6.  Abra la [página Prevención de pérdidas de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies) en el portal de cumplimiento normativo de Microsoft Purview.

7. Elija **crear una directiva de** y crear una directiva DLP de prueba. Vea [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md) si necesita ayuda para crear una directiva. Asegúrese de ejecutarlo en prueba hasta que se sienta cómodo con esta característica. Use estos parámetros para la directiva:
    1. Especifique el ámbito de la regla del examen de la DLP local para ubicaciones específicas si es necesario. Si especifica el ámbito de **ubicaciones** a **Todo**, todos los archivos examinados por el examinador estarán sujetos a la coincidencia y la aplicación de las reglas de DLP.
    1. Al especificar las ubicaciones, puede usar la lista de exclusiones o inclusión. Puede definir que la regla sea relevante solo para las rutas que coincidan con uno de los patrones enumerados en la lista de inclusión o, todos los archivos, excepto los que coincidan con el patrón enumerado en la lista de inclusión. No se admiten rutas locales. Estos son algunos ejemplos de rutas válidas:
      - \\\servidor\recurso compartido
      - \\\server\share\folder1\subfolderabc
      - \*\\carpeta1
      - \*secreto\*.docx
      - \*secreto\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. Estos son algunos ejemplos de uso de valores no aceptados:
      - \*
      - \*\\Un
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> La lista de exclusiones tiene prioridad sobre la lista de inclusiones.

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>Ver las alertas del examinador local de DLP en el panel de administración de alertas de DLP

1. Abra la [página Prevención de pérdidas de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies) en el portal de cumplimiento normativo de Microsoft Purview y seleccione **Alertas**.

2. Consulte los procedimientos descritos en [Configuración y visualización de alertas de las directivas DLP para](dlp-configure-view-alerts-policies.md) ver las alertas de las directivas DLP locales.

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>Ver el examinador local de DLP en el explorador de actividades y el registro de auditoría

> [!NOTE]
> El examinador local requiere que se habilite la auditoría. En Microsoft 365 la auditoría está habilitada de forma predeterminada.

1. Abra la [página Clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) de su dominio en el portal de cumplimiento normativo de Microsoft Purview y seleccione Explorador de actividades.

2. Vea los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para acceder y filtrar todos los datos de las ubicaciones de los examinadores locales.

3. Abra el Buscar el [Registro de auditoría en el Centro de cumplimiento](https://security.microsoft.com/auditlogsearch). Las coincidencias de reglas de DLP están disponibles en la interfaz de usuario del registro del registro de auditoría o mediante [Search-UnifiedAudLog](/powershell/module/exchange/search-unifiedauditlog) en PowerShell. 


## <a name="next-steps"></a>Siguientes pasos
Ahora que ha implementado una directiva de prueba para las ubicaciones locales de DLP y que puede ver los datos de actividad en el Explorador de actividades, está listo para pasar al siguiente paso, donde creará directivas DLP que protejan sus elementos confidenciales.

- [Usar DLP local](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Vea también

- [Obtener información acerca del examinador local de DLP](dlp-on-premises-scanner-learn.md)
- [Usar el examinador local DLP](dlp-on-premises-scanner-use.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
