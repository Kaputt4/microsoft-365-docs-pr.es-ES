---
title: Cumplimiento de comunicaciones con soluciones de SIEM
description: Obtenga información sobre la integración de cumplimiento de comunicaciones con soluciones SIEM.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, cumplimiento de comunicaciones
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 4d9ee561e033e98919063d1f344aa3207a6bb6cd
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66626543"
---
# <a name="communication-compliance-with-siem-solutions"></a>Cumplimiento de comunicaciones con soluciones de SIEM

[El cumplimiento de comunicaciones](communication-compliance.md) es una solución de riesgo interno en Microsoft Purview que ayuda a minimizar los riesgos de comunicación al ayudarle a detectar, capturar y actuar sobre mensajes inadecuados en su organización. Las soluciones de administración de eventos e información de seguridad (SIEM), como [Microsoft Sentinel](https://azure.microsoft.com/services/azure-sentinel) o [Splunk](https://www.splunk.com/) , se usan normalmente para agregar y realizar un seguimiento de las amenazas dentro de una organización.

Una necesidad común para las organizaciones es integrar las alertas de cumplimiento de comunicaciones y estas soluciones SIEM. Con esta integración, las organizaciones pueden ver las alertas de cumplimiento de comunicaciones en su solución SIEM y, a continuación, corregir las alertas dentro del flujo de trabajo de cumplimiento de comunicaciones y la experiencia del usuario. Por ejemplo, un empleado envía un mensaje ofensivo a otro empleado y ese mensaje lo detecta una supervisión de directivas de cumplimiento de comunicaciones para contenido inadecuado. La solución de cumplimiento de comunicaciones realiza un seguimiento de estos eventos en la auditoría de Microsoft 365 (también conocida como "registro de auditoría unificado") y se importa en la solución SIEM. A continuación, se desencadena una alerta en la solución SIEM para la organización a partir de eventos supervisados en la auditoría de Microsoft 365 que están asociados a alertas de cumplimiento de comunicaciones. Los investigadores reciben una notificación de la alerta en las soluciones SIEM y, a continuación, investigan y corrigen la alerta en la solución de cumplimiento de comunicaciones.

## <a name="communication-compliance-alerts-in-microsoft-365-audit"></a>Alertas de cumplimiento de comunicaciones en la auditoría de Microsoft 365

Todas las coincidencias de directivas de cumplimiento de comunicaciones se capturan en Auditoría de Microsoft 365. En los ejemplos siguientes se muestran los detalles disponibles para las actividades de coincidencia de directivas de cumplimiento de comunicaciones seleccionadas:

**Ejemplo de entrada de registro de auditoría para una coincidencia de plantilla de directiva de contenido inadecuado:**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/7/2021 5:30:11 AM
UserIds: user1@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-07T05:30:11","Id":"44e98a7e-57fd-4f89-79b8-08d941084a35","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<HE1P190MB04600526C0524C75E5750C5AC61A9@HE1P190MB0460.EURP190.PROD.OUTLOOK.COM\>","UserId":"user1@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"53be0bf4-75ee-4315-b65d-17d63bdd53ae","SRPolicyName":"Adult images","SRRuleMatchDetails":\[\]}}
ResultIndex: 24
ResultCount: 48
Identity: 44e98a7e-57fd-4f89-79b8-08d941084a35
IsValid: True
ObjectState: Unchanged
```

**Ejemplo de una entrada de registro de auditoría de Microsoft 365 para una directiva con coincidencia de palabra clave personalizada (tipo de información confidencial personalizada):**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/6/2021 9:50:12 PM
UserIds: user2@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-06T21:50:12","Id":"5c61aae5-26fc-4c8e-0791-08d940c8086f","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"public\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<20210706174831.24375086.807067@sailthru.com\>","UserId":"user2@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"a97cf128-c0fc-42a1-88e3-fd3b88af9941","SRPolicyName":"Insiders","SRRuleMatchDetails":\[{"SRCategoryName":"New insiders lexicon"}\]}}
ResultIndex: 46
ResultCount: 48
Identity: 5c61aae5-26fc-4c8e-0791-08d940c8086f
IsValid: True
ObjectState: Unchanged
```

> [!NOTE]
> Actualmente, puede haber un retraso de hasta 24 horas entre el momento en que se registra una coincidencia de directiva en la auditoría de Microsoft 365 y la hora en la que puede investigar las coincidencias de directivas en el cumplimiento de la comunicación.

## <a name="configure-communication-compliance-and-microsoft-sentinel-integration"></a>Configuración del cumplimiento de comunicaciones y la integración de Microsoft Sentinel

Cuando se usa Microsoft Sentinel para agregar coincidencias de directivas de cumplimiento de comunicaciones, Sentinel usa Microsoft 365 Audit como origen de datos. Para integrar alertas de cumplimiento de comunicaciones con Sentinel, siga estos pasos:

1. [Incorporación a Microsoft Sentinel](/azure/sentinel/quickstart-onboard). Como parte del proceso de incorporación, configurará los orígenes de datos.
2. Configure el conector de [datos de Microsoft Sentinel Microsoft Office 365](/azure/sentinel/data-connectors-reference#microsoft-office-365) y, en Configuración del conector, seleccione *Exchange*.
3. Configure la consulta de búsqueda para recuperar las alertas de cumplimiento de comunicaciones. Por ejemplo:

    *| OfficeActivity | where OfficeWorkload == "Exchange" y Operation == "SupervisionRuleMatch" | ordenar por TimeGenerated*

    Para filtrar por un usuario específico, usaría el siguiente formato de consulta:

    *| OfficeActivity | where OfficeWorkload == "Exchange" y Operation == "SupervisionRuleMatch" y UserId == "User1@Contoso.com" | ordenar por TimeGenerated*

Para obtener más información sobre los registros de auditoría de Microsoft 365 para Office 365 recopilados por Microsoft Sentinel, consulte [Referencia de registros de Azure Monitor](/azure/azure-monitor/reference/tables/OfficeActivity).

## <a name="configure-communication-compliance-and-splunk-integration"></a>Configuración del cumplimiento de comunicaciones y la integración de Splunk

Para integrar alertas de cumplimiento de comunicaciones con Splunk, siga estos pasos:

1. Instale el [complemento Splunk para Microsoft Office 365](https://docs.splunk.com/Documentation/AddOns/released/MSO365/ConfigureinputsmanagementAPI)
2. Configuración de una aplicación de integración en Azure AD para el complemento Splunk para Microsoft Office 365
3. Configure las consultas de búsqueda en la solución Splunk. Use el ejemplo de búsqueda siguiente para identificar todas las alertas de cumplimiento de comunicaciones:

    *index=\* sourcetype="o365:management:activity" Workload=Exchange Operation=SupervisionRuleMatch*

Para filtrar los resultados de una directiva de cumplimiento de comunicaciones específica, puede usar el parámetro *SRPolicyMatchDetails.SRPolicyName* .

Por ejemplo, el siguiente ejemplo de búsqueda devolvería alertas de coincidencias a una directiva de cumplimiento de comunicaciones denominada *Contenido inadecuado*:

  *index=\* sourcetype='o365:management:activity' Workload=Exchange Operation=SupervisionRuleMatch SRPolicyMatchDetails.SRPolicyName=\<Inappropriate content\>*

En la tabla siguiente se muestran resultados de búsqueda de ejemplo para diferentes tipos de directiva:

| Tipos de directivas | Resultados de búsqueda de ejemplo |
| :------------------ | :--------------------------------------- |
| Directiva que detecta una lista personalizada de palabras clave de tipo de información confidencial | { <br> CreationTime: 2021-09-17T16:29:57 <br> Identificador: 4b9ce23d-ee60-4f66-f38d-08d979f8631f <br> IsPolicyHit: true <br> Idobjeto: <CY1PR05MB27158B96AF7F3AFE62E1F762CFDD9@CY1PR05MB2715.namprd05.prod.outlook.com> <br> Operación: SupervisiónRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM. Nota","CcsiResults":"leak"} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso.OnMicrosoft.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> Versión: 1 <br> Carga de trabajo: Exchange <br> } |
| Directiva que detecta un lenguaje inadecuado | { <br> CreationTime: 2021-09-17T23:44:35 <br> Identificador: e0ef6f54-9a52-4e4c-9584-08d97a351ad0 <br> IsPolicyHit: true <br> Idobjeto: <BN6PR05MB3571AD9FBB85C4E12C1F66B4CCDD9@BN6PR05MB3571.namprd05.prod.outlook.com> <br> Operación: SupervisiónRuleMatch <br> OrganizationId: d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType: 68 <br> ResultStatus: {"ItemClass":"IPM. Yammer.Message","CcsiResults":""} <br> SRPolicyMatchDetails: { [+] } <br> UserId: user1@contoso.com <br> UserKey: SupervisionStoreDeliveryAgent <br> UserType: 0 <br> Versión: 1 <br> }  |

## <a name="configure-communication-compliance-with-other-siem-solutions"></a>Configuración del cumplimiento de las comunicaciones con otras soluciones SIEM

Para recuperar las coincidencias de directivas de cumplimiento de comunicaciones de Microsoft 365 Audit, puede usar PowerShell o la [API de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

Al usar PowerShell, puede usar cualquiera de estos parámetros con el cmdlet **Search-UnifiedAuditLog** para filtrar los eventos de registro de auditoría para las actividades de cumplimiento de comunicaciones.

| Parámetro de registro de auditoría | Valor del parámetro de cumplimiento de comunicaciones |
| :------------------ | :--------------------------------------- |
| Operaciones          | SupervisionRuleMatch                     |
| RecordType          | ComplianceSupervisionExchange            |

Por ejemplo, a continuación se muestra una búsqueda de ejemplo con el parámetro **Operations** y el valor *SupervisionRuleMatch* :

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch | ft CreationDate,UserIds,AuditData
```
A continuación se muestra una búsqueda de ejemplo con el parámetro **RecordsType** y el valor *ComplianceSupervisionExchange* :

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType ComplianceSuperVisionExchange | ft CreationDate,UserIds,AuditData
```
## <a name="resources"></a>Recursos

- [Auditoría de cumplimiento de comunicaciones](communication-compliance-reports-audits.md#audit)
- [Auditoría de Microsoft Purview (Premium)](advanced-audit.md)
- [Referencia de las API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)
