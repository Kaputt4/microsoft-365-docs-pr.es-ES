---
title: Enumerar incidentes API en Microsoft 365 Defender
description: Obtén información sobre cómo enumerar incidentes API en Microsoft 365 Defender
keywords: lista, incidentes, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572158"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Enumerar incidentes API en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.


## <a name="api-description"></a>Descripción de la API

La API de incidentes de lista le permite ordenar incidentes para crear una respuesta informada de ciberseguridad. Expone una colección de incidentes que se marcaron en la red, dentro del intervalo de tiempo especificado en la directiva de retención de entorno. Los incidentes más recientes se muestran en la parte superior de la lista. Cada incidente contiene una matriz de alertas relacionadas y sus entidades relacionadas.

La API admite los siguientes operadores **de OData:**

- `$filter` en el `lastUpdateTime` , , , y `createdTime` `status` `assignedTo` propiedades
- `$top`, con un valor máximo de **100**
- `$skip`

## <a name="limitations"></a>Limitaciones

1. El tamaño máximo de página es **de 100 incidentes.**
2. La tarifa máxima de solicitudes es de **50 llamadas por minuto** y **1500 llamadas por hora.**

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Api de Access Microsoft 365 Defender](api-access.md)

Tipo de permiso | Permiso | Nombre para mostrar del permiso
-|-|-
Aplicación | Incidente.Leer.Todo | Lea todos los incidentes
Aplicación | Incident.ReadWrite.All | Leer y escribir todos los incidentes
Delegado (cuenta profesional o educativa) | Incidente.Leer | Leer incidentes
Delegado (cuenta profesional o educativa) | Incident.ReadWrite | Leer y escribir incidentes

> [!Note]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener permiso de vista para incidentes en el portal.
> - La respuesta solo incluirá incidentes a los que el usuario está expuesto.

## <a name="http-request"></a>Solicitud HTTP

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
-|-|-
Authorization | Cadena | Portador {token}. **Required**


## <a name="request-body"></a>Cuerpo de la solicitud

Ninguna.

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve `200 OK` y una lista de [incidentes](api-incident.md) en el cuerpo de la respuesta.

## <a name="schema-mapping"></a>Asignación de esquemas

### <a name="incident-metadata"></a>Metadatos del incidente

Nombre del campo | Descripción | Valor de ejemplo
-|-|-
incidenteId | Identificador único para representar el incidente | 924565
redirectIncidentId | Solo se rellena en caso de que se esté agrupando un incidente junto con otro incidente, como parte de la lógica de procesamiento de incidentes. | 924569
incidentName | Valor de cadena disponible para cada incidente. | Actividad de ransomware
creóTime | Momento en que se creó el incidente por primera vez. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Hora en que el incidente se actualizó por última vez en el back-end.<br /><br /> Este campo se puede usar al establecer el parámetro request para el intervalo de tiempo en que se recuperan los incidentes. | 2020-09-06T14:46:57.29Z
assignedTo | Propietario del incidente, o *nulo* si no se asigna ningún propietario. | secop2@contoso.com
classification | La especificación del incidente. Los valores de propiedad son: *Unknown*, *FalsePositive*, *TruePositive* | Unknown
determinación | Especifica la determinación del incidente. Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Otros* | Nodisponible
status | Categorize incidentes (como *Activos* o *Resueltos).* Puede ayudarle a organizar y administrar su respuesta a incidentes. | Activa
severity | Indica el posible impacto en los activos. Cuanto mayor sea la gravedad, mayor será el impacto. Por lo general, los elementos de mayor gravedad requieren la atención más inmediata.<br /><br />Uno de los siguientes valores: *Informativo,* *Bajo,**Medio y *Alto*. | Medio
tags | Matriz de etiquetas personalizadas asociadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común. | \[\]
comments | Matriz de comentarios creados por secops al administrar el incidente, por ejemplo, información adicional sobre la selección de clasificación. | \[\]
alerts | Matriz que contiene todas las alertas relacionadas con el incidente, además de otra información, como la gravedad, las entidades que participaron en la alerta y el origen de las alertas. | \[\] (consulte los detalles sobre los campos de alerta a continuación)

### <a name="alerts-metadata"></a>Alertas de metadatos

Nombre del campo | Descripción | Valor de ejemplo
-|-|-
alertId | Identificador único para representar la alerta | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidenteId | Identificador único para representar el incidente con el que está asociada esta alerta | 924565
serviceSource | Servicio del que se origina la alerta, como Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity o Microsoft Defender para Office 365. | MicrosoftCloudAppSecurity
creationTime | Hora en la que se creó la alerta por primera vez. | 2020-09-06T14:46:55.7182276Z
última Hora de la Constitución | Hora en la que la alerta se actualizó por última vez en el back-end. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Hora en que se resolvió la alerta. | 2020-09-10T05:22:59Z
primeraActivity | Momento en que la alerta informó por primera vez de que la actividad se actualizó en el back-end.| 2020-09-04T05:22:59Z
title | Breve valor de cadena de identificación disponible para cada alerta. | Actividad de ransomware
description | Valor de cadena que describe cada alerta. | El usuario Test User2 (testUser2@contoso.com) manipuló 99 archivos con varias extensiones que terminan con la extensión poco común *herunterladen*. Este es un número inusual de manipulaciones de archivos y es indicativo de un posible ataque ransomware.
categoría | Vista visual y numérica de hasta dónde ha progresado el ataque a lo largo de la cadena de muerte. Alineado con el [marco MITRE ATT&CK™](https://attack.mitre.org/). | Impacto
status | Categorize las alertas (como *Nuevo,* *Activo* o *Resuelto).* Puede ayudarle a organizar y administrar su respuesta a las alertas. | Nueva
severity | Indica el posible impacto en los activos. Cuanto mayor sea la gravedad, mayor será el impacto. Por lo general, los elementos de mayor gravedad requieren la atención más inmediata.<br>Uno de los siguientes valores: *Informativo,* *Bajo,**Medio y *Alto*. | Medio
investigaciónId | El ID de investigación automatizado desencadenado por esta alerta. | 1234
investigaciónState | Información sobre el estado actual de la investigación. Uno de los siguientes valores: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | UnsupportedAlertType
classification | La especificación del incidente. Los valores de propiedad son: *Unknown*, *FalsePositive*, *TruePositive* o *null* | Unknown
determinación | Especifica la determinación del incidente. Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Otro* o  *null* | apropiado
assignedTo | Propietario del incidente, o *nulo* si no se asigna ningún propietario. | secop2@contoso.com
actorName | El grupo de actividad, si existe, el asociado a esta alerta. | boro
amenazaFamilyName | Familia de amenazas asociada con esta alerta. | nulo
mitreTechniques | Las técnicas de ataque, alineadas con el marco de ™ DE&[CK de MITRE ATT.](https://attack.mitre.org/) | \[\]
Dispositivos | Todos los dispositivos donde se enviaron alertas relacionadas con el incidente. | \[\] (consulte los detalles sobre los campos de entidad a continuación)

### <a name="device-format"></a>Formato de dispositivo

Nombre del campo | Descripción | Valor de ejemplo
-|-|-
DeviceId | El identificador de dispositivo designado en Microsoft Defender para endpoint. | 24c22b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  El ID de dispositivo designado en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Solo disponible para dispositivos unidos a un dominio. | nulo
deviceDnsName | El nombre de dominio completo para el dispositivo. | user5cx.middleeast.corp.contoso.com
osPlatform | La plataforma del sistema operativo que está ejecutando el dispositivo.| WindowsServer2016
osBuild | La versión de compilación para el sistema operativo que está ejecutando el dispositivo. | 14393
rbacGroupName | El grupo [de control de acceso basado en](/azure/role-based-access-control/overview) roles (RBAC) asociado al dispositivo. | WDATP-Ring0
firstSeen | Hora en que se vio el dispositivo por primera vez. | 2020-02-06T14:16:01.9330135Z
healthStatus | El estado de mantenimiento del dispositivo. | Activa
riskScore | La puntuación de riesgo del dispositivo. | Alta
Entidades | Todas las entidades que se han identificado como parte de una alerta determinada o relacionadas con ellos. | \[\] (consulte los detalles sobre los campos de entidad a continuación)

### <a name="entity-format"></a>Formato de entidad

Nombre del campo | Descripción | Valor de ejemplo
-|-|-
entityType | Entidades que se han identificado como parte de una alerta determinada o relacionadas con ellos.<br>Los valores de propiedades son: *Usuario*, *Ip*, *Url*, *Archivo*, *Proceso*, *MailBox*, *MailMessage*, *MailCluster*, *Registro* | Usuario
sha1 | Disponible si entityType es *File*.<br>El hash de archivo para alertas asociadas a un archivo o proceso. | 5de839186691a96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Disponible si entityType es *File*.<br>El hash de archivo para alertas asociadas a un archivo o proceso. | 28cb017dfc99073a1b47c1b30f413e3ce774c491eb4158de50f9dbb36d8043
fileName | Disponible si entityType es *File*.<br>El nombre de archivo de las alertas asociadas a un archivo o proceso | Detector.UnitTests.dll
archivoPath | Disponible si entityType es *File*.<br>La ruta de acceso del archivo para las alertas asociadas a un archivo o proceso | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Disponible si entityType es *Process*. | 24348
procesoCommandLine | Disponible si entityType es *Process*. | "Su archivo está listo para descargar \_1911150169.exe"
procesoCreationTime | Disponible si entityType es *Process*. | 2020-07-18T03:25:38.5269993Z
parentProcessId | Disponible si entityType es *Process*. | 16840
parentProcessCreationTime | Disponible si entityType es *Process*. | 2020-07-18T02:12:32.8616797Z
ipAddress | Disponible si entityType es *Ip*. <br>Dirección IP para alertas asociadas a eventos de red, como *Comunicación a un destino de red malintencionado.* | 62.216.203.204
url | Disponible si entityType es *Url*. <br>Url para alertas asociadas a eventos de red, como *Comunicación a un destino de red malintencionado.* | down.esales360.cn
accountName | Disponible si entityType es *User*. | testUser2
domainName | Disponible si entityType es *User*. | europe.corp.contoso
userSid | Disponible si entityType es *User*. | S-1-5-21-1721254763-462695806-15388882281-4156657
aadUserId | Disponible si entityType es *User*. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Disponible si entityType es  / *User MailBox* / *MailMessage*. | testUser2@contoso.com
buzónDisplayName | Disponible si entityType es *MailBox*. | prueba User2
buzónAddress | Disponible si entityType es  / *User MailBox* / *MailMessage*. | testUser2@contoso.com
clusterPor | Disponible si entityType es  *MailCluster*. | Sujeto; P2SenderDomain; ContentType
sender | Disponible si entityType es  / *User MailBox* / *MailMessage*. | user.abc@mail.contoso.co.in
destinatario | Disponible si entityType es *MailMessage*. | testUser2@contoso.com
subject | Disponible si entityType es *MailMessage*. | \[Atención EXTERNA \]
deliveryAction | Disponible si entityType es *MailMessage*. | entregado
securityGroupId | Disponible si entityType es  *SecurityGroup*. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Disponible si entityType es  *SecurityGroup*. | Operadores de configuración de red
registryHive | Disponible si entityType es  *el Registro*. | MÁQUINA LOCAL HKEY \_ \_ |
registryKey | Disponible si entityType es  *el Registro*. | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Disponible si entityType es  *el Registro*. | Cadena
registryValue | Disponible si entityType es  *el Registro*. | 31-00-00-00
deviceId | El ID, si existe, del dispositivo relacionado con la entidad. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Ejemplo

**Solicitud**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**Respuesta**

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
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
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

- [Acceda a las API de Microsoft 365 Defender](api-access.md)
- [Obtenga información sobre los límites de api y las licencias](api-terms.md)
- [Comprender los códigos de error](api-error-codes.md)
- [Información general sobre incidentes](incidents-overview.md)
- [API de incidentes](api-incident.md)
- [Actualizar api incidentes](api-update-incidents.md)
