---
title: Uso de un escáner local de prevención de pérdida de datos
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
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo usar la prevención de pérdidas de datos en el escáner local para examinar datos en reposo e implementar acciones de protección para recursos compartidos de archivos locales y carpetas y bibliotecas de documentos de SharePoint locales.
ms.openlocfilehash: ae5ffce9e664ada6e7476bb02b40f4a5c279d441
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624187"
---
# <a name="use-the-data-loss-prevention-on-premises-scanner"></a>Uso del escáner local de prevención de pérdida de datos

Para ayudarle a familiarizarse con las características locales de prevención de pérdidas de datos de Microsoft Purview y cómo aparecen en las directivas DLP, hemos creado algunos escenarios que puede seguir.

> [!IMPORTANT]
> Estos escenarios DLP locales no son los procedimientos oficiales para crear y optimizar directivas DLP. Consulte los temas siguientes cuando necesite trabajar con directivas DLP en situaciones generales:
>
> - [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
> - [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)
> - [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
> - [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>Escenario: Descubrir los archivos que coinciden con las reglas DLP

Los datos del examinador de DLP local aparecen en varias áreas

#### <a name="activity-explorer"></a>Explorador de actividad

 Microsoft DLP para el entorno local detecta coincidencias de reglas DLP e informa de ellas en [Explorador de actividad](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).

#### <a name="microsoft-365-audit-log"></a>Registro de auditoría de Microsoft 365

Las coincidencias de reglas DLP están disponibles en la interfaz de usuario del registro de auditoría; consulte [Buscar en el registro de auditoría en el portal de cumplimiento normativo de Microsoft Purview](search-the-audit-log-in-security-and-compliance.md)  o accesible mediante [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell.

#### <a name="aip"></a>AIP

Los datos de descubrimiento legal están disponibles en un informe local en formato CSV que se almacena en:

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 Busque las columnas siguientes:

- Modo de DLP
- Estado de DLP
- Comentario de DLP
- Nombre de regla DLP
- Acciones DLP
- Propietario
- Permisos NTFS actuales (SDDL)
- Permisos NTFS aplicados (SDDL)
- Tipo de permisos NTFS

### <a name="scenario-enforce-dlp-rule"></a>Escenario: exigir regla DLP

Si quiere exigir las reglas DLP en los archivos examinados, debe habilitarse la obligación de aplicarlas en el trabajo de análisis de contenido en AIP y a nivel de directiva en DLP.

#### <a name="configure-dlp-to-enforce-policy-actions"></a>Configurar DLP para obligar a aplicar acciones de directiva

1. Abra la página [Prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies) y seleccione la directiva DLP dirigida a los repositorios de ubicación locales que haya configurado en AIP.
2. Edite la directiva.
3. En la página **Probar o habilitar la directiva**, seleccione **Sí, activar inmediatamente**.

## <a name="see-also"></a>Vea también

- [Obtener información acerca del examinador local de DLP](dlp-on-premises-scanner-learn.md)
- [Introducción al examinador local DLP](dlp-on-premises-scanner-get-started.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
