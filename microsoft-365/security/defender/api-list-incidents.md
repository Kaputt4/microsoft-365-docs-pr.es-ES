---
title: Enumerar la API de incidentes en Microsoft 365 Defender
description: Aprenda a enumerar la API de incidentes en Microsoft 365 Defender
keywords: list, incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: d86c26af54c4cd69e65cd5af952556a2553b728e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483066"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Enumerar la API de incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="api-description"></a>Descripción de la API

La API de lista de incidentes le permite ordenar los incidentes para crear una respuesta de ciberseguridad informada. Expone una colección de incidentes marcados en la red, dentro del intervalo de tiempo especificado en la directiva de retención del entorno. Los incidentes más recientes se muestran en la parte superior de la lista. Cada incidente contiene una matriz de alertas relacionadas y sus entidades relacionadas.

La API admite los siguientes operadores **de OData** :

- `$filter`en las `lastUpdateTime`propiedades , `createdTime`, `status`y `assignedTo`
- `$top`, con un valor máximo de **100**
- `$skip`

## <a name="limitations"></a>Limitaciones

1. El tamaño máximo de página es **de 100 incidentes**.
2. La tasa máxima de solicitudes es **de 50 llamadas por minuto** y **1500 llamadas por hora**.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Access Microsoft 365 Defender API](api-access.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Incident.Read.All|Leer todos los incidentes
Application|Incident.ReadWrite.All|Leer y escribir todos los incidentes
Delegado (cuenta profesional o educativa)|Incident.Read|Leer incidentes
Delegado (cuenta profesional o educativa)|Incident.ReadWrite|Incidentes de lectura y escritura

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener permiso de visualización para incidentes en el portal.
> - La respuesta solo incluirá incidentes a los que esté expuesto el usuario.

## <a name="http-request"></a>Solicitud HTTP

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre|Tipo|Descripción
---|---|---
Authorization|Cadena|Portador {token}. **Required**

## <a name="request-body"></a>Cuerpo de la solicitud

Ninguna.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve `200 OK`y una lista de [incidentes](api-incident.md) en el cuerpo de la respuesta.

## <a name="schema-mapping"></a>Asignación de esquemas

### <a name="incident-metadata"></a>Metadatos de incidentes

Nombre del campo|Descripción|Valor de ejemplo
---|---|---
incidentId|Identificador único para representar el incidente|924565
redirectIncidentId|Solo se rellena en caso de que un incidente se agrupe junto con otro incidente, como parte de la lógica de procesamiento de incidentes.|924569
incidentName|Valor de cadena disponible para cada incidente.|Actividad de ransomware
createdTime|Hora en que se creó el incidente por primera vez.|2020-09-06T14:46:57.0733333Z
lastUpdateTime|Hora a la que se actualizó por última vez el incidente en el back-end. <p> Este campo se puede usar al establecer el parámetro de solicitud para el intervalo de tiempo que se recuperan los incidentes.|2020-09-06T14:46:57.29Z
assignedTo|Propietario del incidente o *null* si no se asigna ningún propietario.|secop2@contoso.com
classification|Especificación del incidente. Los valores de propiedad son: *Unknown*, *FalsePositive*, *TruePositive*|Unknown
Determinación|Especifica la determinación del incidente. Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*|No disponible
detectionSource|Especifica el origen de la detección.|Defender for Cloud Apps
status|Clasifique los incidentes (como *Activos* o *Resueltos*). Puede ayudarle a organizar y administrar la respuesta a incidentes.|Activo
severity|Indica el posible impacto en los recursos. Cuanto mayor sea la gravedad, mayor será el impacto. Normalmente, los elementos de gravedad más altos requieren la atención más inmediata. <p> Uno de los valores siguientes: *Informativo*, *Bajo*, *Medio y *Alto*.|Mediano
tags|Matriz de etiquetas personalizadas asociadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común.|\[\]
comments|Matriz de comentarios creados por secops al administrar el incidente, por ejemplo, información adicional sobre la selección de clasificación.|\[\]
alertas|Matriz que contiene todas las alertas relacionadas con el incidente, además de otra información, como la gravedad, las entidades implicadas en la alerta y el origen de las alertas.|\[\] (consulte los detalles sobre los campos de alerta a continuación)

### <a name="alerts-metadata"></a>Metadatos de alertas

Nombre del campo|Descripción|Valor de ejemplo
---|---|---
alertId|Identificador único para representar la alerta|caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId|Identificador único para representar el incidente al que está asociada esta alerta|924565
serviceSource|Servicio del que se origina la alerta, como Microsoft Defender para punto de conexión, Microsoft Defender for Cloud Apps, Microsoft Defender for Identity o Microsoft Defender para Office 365.|MicrosoftCloudAppSecurity
creationTime|Hora en que se creó la alerta por primera vez.|2020-09-06T14:46:55.7182276Z
lastUpdatedTime|Hora a la que se actualizó por última vez la alerta en el back-end.|2020-09-06T14:46:57.2433333Z
resolvedTime|Hora en que se resolvió la alerta.|2020-09-10T05:22:59Z
firstActivity|Hora en que la alerta informó por primera vez de que la actividad se actualizó en el back-end.|2020-09-04T05:22:59Z
title|Breve valor de cadena de identificación disponible para cada alerta.|Actividad de ransomware
description|Valor de cadena que describe cada alerta.|El usuario Test User2 (testUser2@contoso.com) manipuló 99 archivos con varias extensiones que terminan con la extensión poco común *herunterladen*. Este es un número inusual de manipulaciones de archivos y es indicativo de un posible ataque ransomware.
categoría|Vista visual y numérica de hasta dónde ha progresado el ataque a lo largo de la cadena de eliminación. Alineado con el [marco de trabajo de MITRE ATT&CK™](https://attack.mitre.org/).|Impacto
status|Clasifique las alertas (como *Nuevas*, *Activas* o *Resueltas*). Puede ayudarle a organizar y administrar la respuesta a las alertas.|Nueva
severity|Indica el posible impacto en los recursos. Cuanto mayor sea la gravedad, mayor será el impacto. Normalmente, los elementos de gravedad más altos requieren la atención más inmediata.<br>Uno de los valores siguientes: *Informativo*, *Bajo*, *Medio* y *Alto*.|Mediano
investigationId|Identificador de investigación automatizado desencadenado por esta alerta.|1234
investigationState|Información sobre el estado actual de la investigación. Uno de los siguientes valores: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.|UnsupportedAlertType
classification|Especificación del incidente. Los valores de propiedad son: *Unknown*, *FalsePositive*, *TruePositive* o *null*|Unknown
Determinación|Especifica la determinación del incidente. Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* o  *null*|Apt
assignedTo|Propietario del incidente o *null* si no se asigna ningún propietario.|secop2@contoso.com
actorName|El grupo de actividad, si existe, asociado a esta alerta.|BORO
threatFamilyName|Familia de amenazas asociada a esta alerta.|nulo
mitreTechniques|Las técnicas de ataque, según se alinean con el marco [de trabajo de MITRE ATT&CK](https://attack.mitre.org/)™.|\[\]
dispositivos|Todos los dispositivos en los que se enviaron alertas relacionadas con el incidente.|\[\] (consulte los detalles sobre los campos de entidad a continuación)

### <a name="device-format"></a>Formato de dispositivo

Nombre del campo|Descripción|Valor de ejemplo
---|---|---
DeviceId|Identificador de dispositivo designado en Microsoft Defender para punto de conexión.|24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId|Identificador de dispositivo designado en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Solo está disponible para dispositivos unidos a un dominio.|nulo
deviceDnsName|Nombre de dominio completo para el dispositivo.|user5cx.middleeast.corp.contoso.com
osPlatform|Plataforma del sistema operativo en la que se ejecuta el dispositivo.|WindowsServer2016
osBuild|Versión de compilación del sistema operativo en ejecución del dispositivo.|14393
rbacGroupName|El grupo [de control de acceso basado en rol](/azure/role-based-access-control/overview) (RBAC) asociado al dispositivo.|WDATP-Ring0
firstSeen|Hora en que se vio el dispositivo por primera vez.|2020-02-06T14:16:01.9330135Z
healthStatus|Estado de mantenimiento del dispositivo.|Activo
riskScore|Puntuación de riesgo del dispositivo.|Alto
Entidades|Todas las entidades que se han identificado para formar parte o estar relacionadas con una alerta determinada.|\[\] (consulte los detalles sobre los campos de entidad a continuación)

### <a name="entity-format"></a>Formato de entidad

Nombre del campo|Descripción|Valor de ejemplo
---|---|---
Entitytype|Entidades que se han identificado como parte o relacionadas con una alerta determinada.<br>Los valores de propiedades son: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*|User
sha1|Disponible si entityType es *File*.<br>Hash de archivo para las alertas asociadas a un archivo o proceso.|5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256|Disponible si entityType es *File*.<br>Hash de archivo para las alertas asociadas a un archivo o proceso.|28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName|Disponible si entityType es *File*.<br>Nombre de archivo de las alertas asociadas a un archivo o proceso|Detector.UnitTests.dll
Filepath|Disponible si entityType es *File*.<br>Ruta de acceso del archivo para las alertas asociadas a un archivo o proceso|C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId|Disponible si entityType es *Process*.|24348
processCommandLine|Disponible si entityType es *Process*.|"El archivo está listo para descargar\_1911150169.exe"
processCreationTime|Disponible si entityType es *Process*.|2020-07-18T03:25:38.5269993Z
parentProcessId|Disponible si entityType es *Process*.|16840
parentProcessCreationTime|Disponible si entityType es *Process*.|2020-07-18T02:12:32.8616797Z
ipAddress|Disponible si entityType es *Ip*. <br>Dirección IP de las alertas asociadas a eventos de red, como *la comunicación con un destino de red malintencionado*.|62.216.203.204
url|Disponible si entityType es *Url*. <br>Dirección URL de las alertas asociadas a eventos de red, como *la comunicación con un destino de red malintencionado*.|down.esales360.cn
accountName|Disponible si entityType es *User*.|testUser2
domainName|Disponible si entityType es *User*.|europe.corp.contoso
userSid|Disponible si entityType es *User*.|S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId|Disponible si entityType es *User*.|fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName|Disponible si entityType es *User*/*MailBox*/*MailMessage*.|testUser2@contoso.com
mailboxDisplayName|Disponible si entityType es *MailBox*.|probar User2
mailboxAddress|Disponible si entityType es *User*/*MailBox*/*MailMessage*.|testUser2@contoso.com
clusterBy|Disponible si entityType es  *MailCluster*.|Sujeto; P2SenderDomain; Contenttype
sender|Disponible si entityType es *User*/*MailBox*/*MailMessage*.|user.abc@mail.contoso.co.in
destinatario|Disponible si entityType es *MailMessage*.|testUser2@contoso.com
subject|Disponible si entityType es *MailMessage*.|\[Atención externa\]
deliveryAction|Disponible si entityType es *MailMessage*.|Entregado
securityGroupId|Disponible si entityType es  *SecurityGroup*.|301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName|Disponible si entityType es  *SecurityGroup*.|Operadores de configuración de red
registryHive|Disponible si entityType es  *Registry*.|HKEY\_LOCAL\_MACHINE|
registryKey|Disponible si entityType es  *Registry*.|SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType|Disponible si entityType es  *Registry*.|Cadena
registryValue|Disponible si entityType es  *Registry*.|31-00-00-00
deviceId|Identificador, si existe, del dispositivo relacionado con la entidad.|986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

### <a name="response-example"></a>Ejemplo de respuesta

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Microsoft Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>Artículos relacionados

- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Más información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [Información general sobre incidentes](incidents-overview.md)
- [API de incidentes](api-incident.md)
- [Actualización de la API de incidentes](api-update-incidents.md)
