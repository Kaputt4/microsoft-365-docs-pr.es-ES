---
title: API de lista de incidentes en Microsoft 365 defender
description: Obtenga información sobre cómo enumerar la API de incidentes en Microsoft 365 defender
keywords: lista, incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9da6fdf04fd22767f3984229b7862f02b8293067
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845001"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>API de lista de incidentes en Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**

- Microsoft 365 defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Descripción de la API

La API de incidentes permite ordenar los incidentes para priorizar y crear una respuesta Cybersecurity informada. Expone una colección de incidentes que se marcaron desde dispositivos, cuentas de correo electrónico y usuarios de la red, dentro del intervalo de tiempo especificado en la Directiva de retención del entorno. Los incidentes más recientes se muestran en la parte superior de la lista. Cada incidente contiene una matriz de alertas relacionadas y sus entidades relacionadas.

<br>La API admite los siguientes operadores **OData** :
<br>```$filter``` on: ```lastUpdateTime``` , ```createdTime``` ```status``` y ```assignedTo``` propiedades.
<br>```$top``` con valor máximo de **100**
<br>```$skip```

## <a name="limitations"></a>Limitaciones

1. El tamaño máximo de página es de **100 incidentes**.
2. La tasa de solicitudes máxima es de **50 llamadas por minuto** y **1500 de llamadas por hora**.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Access Microsoft 365 API de defender](api-access.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar del permiso
:---|:---|:---
Aplicación |   Incident. Read. All | ' Leer todos los incidentes '
Aplicación |   Incident. ReadWrite. All | ' Leer y escribir todos los incidentes '
Delegado (cuenta profesional o educativa) | Incident. Read | ' Incidentes de lectura '
Delegado (cuenta profesional o educativa) | Incident. ReadWrite | ' Incidentes de lectura y escritura '

> [!Note]
> Al obtener un token con credenciales de usuario:
> - El usuario debe tener permiso de visualización para incidentes en el portal.
> - La respuesta solo incluirá los incidentes a los que el usuario está expuesto.

## <a name="http-request"></a>Solicitud HTTP

```
GET /api/incidents
```

## <a name="request-headers"></a>Encabezados de solicitud

Nombre | Tipo | Descripción
:---|:---|:---
Authorization | Cadena | {Token} de portador. **Necesario**.


## <a name="request-body"></a>Cuerpo de la solicitud
Ninguna.

## <a name="response"></a>Respuesta
Si se ejecuta correctamente, este método devuelve 200 OK y una lista de [incidentes](api-incident.md) en el cuerpo de la respuesta.

## <a name="schema-mapping"></a>Asignación del esquema

| Nombre del campo                                | Description                                                                                                                                                                                                                                                                                                                                                                                | Valor de ejemplo                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Metadatos del incidente**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| incidentId                                | Identificador único que representa el incidente.                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | Solo se rellena en caso de que un incidente se agrupe con otro incidente, como parte de la lógica de procesamiento de incidentes.                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| incidentName                              | Valor de cadena disponible para cada incidente.                                                                                                                                                                                                                                                                                                                                                  | Actividad de ransomware                                                                                                                                                                                                                               |
| createdTime                               | Hora a la que se creó el incidente por primera vez.                                                                                                                                                                                                                                                                                                                                                      | 2020-09-06T14:46:57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | Hora en que se actualizó por última vez el incidente en el back-end.<br> Este campo se puede usar al establecer el parámetro de solicitud para el intervalo de tiempo durante el que se recuperan los incidentes.                                                                                                                                                                                                                      | 2020-09-06T14:46:57.29 Z                                                                                                                                                                                                                           |
| assignedTo                                | Propietario del incidente, o *null* si no hay ningún propietario asignado.                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| classification                            | La especificación del incidente. Los valores de la propiedad son: *Unknown* , *FalsePositive* , *TruePositive*                                                                                                                                                                                                                                                                           | Desconocido                                                                                                                                                                                                                                           |
| cálculo                             | Especifica la determinación del incidente. Los valores de la propiedad son: *NotAvailable* , *apt* , *malware* , *SecurityPersonnel* , *SecurityTesting* , *UnwantedSoftware* , *other*                                                                                                                                                                                                                | NotAvailable                                                                                                                                                                                                                                      |
| status                                    | Clasifique los incidentes (como *activos* o *resueltos* ). Esto le ayudará a organizar y administrar la respuesta a incidentes.                                                                                                                                                                                                                                                                  | Activo                                                                                                                                                                                                                                            |
| severity                                  | Indica el posible impacto en los activos. Cuanto mayor sea la gravedad, mayor será el impacto. Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.<br>Uno de los siguientes valores: *informativo* , *bajo* , * medio y *alto*.                                                                                                                                | Mediano                                                                                                                                                                                                                                            |
| tags                                      | Matriz de etiquetas personalizadas asociadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común.                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| alerts                                    | Matriz de todas las alertas relacionadas con el incidente y otra información, como la gravedad, las entidades implicadas en la alerta, el origen de las alertas.                                                                                                                                                                                                                     | \[\] (consulte los detalles de los campos de alerta a continuación)                                                                                                                                                                                                          |
| **Metadatos de alertas**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| alertId                                   | Identificador único que representa la alerta                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| incidentId                                | Identificador único que representa el incidente al que está asociada esta alerta                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| serviceSource                             | Servicio del que procede la alerta, como Microsoft defender para el punto de conexión, Microsoft Cloud App Security, Microsoft defender para identidad o Microsoft defender para Office 365.                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| creationTime                              | Hora a la que se creó la alerta por primera vez.                                                                                                                                                                                                                                                                                                                                                         | 2020-09-06T14:46:55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | Hora de la última actualización de la alerta en el back-end.                                                                                                                                                                                                                                                                                                                                           | 2020-09-06T14:46:57.2433333 Z                                                                                                                                                                                                                      |
| resolvedTime                              | Hora a la que se resolvió la alerta.                                                                                                                                                                                                                                                                                                                                                              | 2020-09-10T05:22:59Z                                                                                                                                                                                                                              |
| firstActivity                             | Hora en que la alerta notificó por primera vez que se actualizó la actividad en el back-end.                                                                                                                                                                                                                                                                                                                             | 2020-09-04T05:22:59Z                                                                                                                                                                                                                              |
| title                                     | Valor de cadena de identificación breve disponible para cada alerta.                                                                                                                                                                                                                                                                                                                                                     | Actividad de ransomware                                                                                                                                                                                                                               |
| description                               | Valor de cadena que describe cada alerta.                                                                                                                                                                                                                                                                                                                                                        | El usuario de prueba user2 (testUser2@contoso.com) ha manipulado 99 archivos con varias extensiones que finalizan con la extensión no común *herunterladen*. Se trata de un número inusual de manipulaciones de archivos e indica un posible ataque de ransomware. |
| categoría                                  | Vista visual y numérica de cuánto ha progresado el ataque a lo largo de la cadena de eliminación. Se alinea a la [Mitre de ATT&CK™ Framework](https://attack.mitre.org/).                                                                                                                                                                                                                           | Impacto                                                                                                                                                                                                                                            |
| status                                    | Clasifique las alertas (como *nuevas* , *activas* o *resueltas* ). Esto le ayudará a organizar y administrar la respuesta a las alertas.                                                                                                                                                                                                                                                                   | Nuevo                                                                                                                                                                                                                                               |
| severity                                  | Indica el posible impacto en los activos. Cuanto mayor sea la gravedad, mayor será el impacto. Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.<br>Uno de los siguientes valores: *informativo* , *bajo* , * medio y *alto*.                                                                                                                                   | Mediano                                                                                                                                                                                                                                            |
| investigationId                           | El identificador de investigación automatizada desencadenada por esta alerta.                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | Información sobre el estado actual de la investigación. Uno de los siguientes: *Unknown* , *terminated* , *SuccessfullyRemediated* , *benigno* , *failed* , *PartiallyRemediated* , *Running* , *PendingApproval* , *PendingResource* , *PartiallyInvestigated* , *TerminatedByUser* , *TerminatedBySystem* , *queued* , *InnerFailure* , *PreexistingAlert* , *unsupports* , *UnsupportedAlertType* *, SuppressedAlert.* | UnsupportedAlertType                                                                                                                                                                                                                              |
| classification                            | La especificación del incidente. Los valores de la propiedad son: *Unknown* , *FalsePositive* , *TruePositive* o *null*                                                                                                                                                                                                                                                                   | Desconocido                                                                                                                                                                                                                                           |
| cálculo                             | Especifica la determinación del incidente. Los valores de la propiedad son: *NotAvailable* , *apt* , *malware* , *SecurityPersonnel* , *SecurityTesting* , *UnwantedSoftware* , *other* o  *null*                                                                                                                                                                                                     | Apt                                                                                                                                                                                                                                               |
| assignedTo                                | Propietario del incidente, o *null* si no hay ningún propietario asignado.                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actorName                                 | El grupo de actividad, si lo hubiera, asociado con esta alerta.                                                                                                                                                                                                                                                                                                                                        | BORO                                                                                                                                                                                                                                             |
| threatFamilyName                          | Familia de amenazas asociada a esta alerta.                                                                                                                                                                                                                                                                                                                                                   | nulo                                                                                                                                                                                                                                              |
| mitreTechniques                           | Las técnicas de ataque, que se alinean con el marco de [Mitre ATT&CK](https://attack.mitre.org/)™.                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| equipos                                   | Todos los dispositivos en los que se enviaron alertas relacionadas con el incidente.                                                                                                                                                                                                                                                                                                     | \[\] (vea los detalles de los campos de entidad a continuación)                                                                                                                                                                                                         |
| **Formato de dispositivo**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | IDENTIFICADOR del dispositivo según se ha designado en Microsoft defender para el punto de conexión.                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  El identificador de dispositivo tal como se ha designado en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD). Solo está disponible para los dispositivos Unidos a un dominio.                                                                                                                                                                                                                                                                                                                              | nulo                                                                                                                                                                                                                                              |
| deviceDnsName                             | Nombre de dominio completo del dispositivo.                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | La plataforma de sistema operativo que el dispositivo está ejecutando.                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | La versión de compilación para el sistema operativo que el dispositivo está ejecutando.                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | El grupo [de control de acceso basado en roles](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) asociado al dispositivo.                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | Hora en que se ha visto el dispositivo por primera vez.                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06T14:16:01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | El estado de mantenimiento del dispositivo.                                                                                                                                                                                                                                                                                                                                                                        | Activo                                                                                                                                                                                                                                            |
| riskScore                                 | La puntuación de riesgo para el dispositivo.                                                                                                                                                                                                                                                                                                                                                                       | Alto                                                                                                                                                                                                                                              |
| organismos                                  | Todas las entidades que se han identificado como parte de una alerta determinada o están relacionadas con ella.                                                                                                                                                                                                                                                                                | \[\] (vea los detalles de los campos de entidad a continuación)                                                                                                                                                                                                         |
| **Formato de la entidad**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| entityType                                | Entidades que se han identificado como parte de una alerta determinada o están relacionadas con ella.<br>Los valores de las propiedades son: *usuario* , *IP* , *dirección URL* , *archivo* , *proceso* , *buzón* , *MailMessage* , *MailCluster* , *registro*                                                                                                                                                                                                     | Usuario                                                                                                                                                                                                                                              |
| SHA1                                      | Disponible si entityType es *File*.<br>Hash de archivo de alertas asociadas a un archivo o proceso.                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| SHA256                                    | Disponible si entityType es *File*.<br>Hash de archivo de alertas asociadas a un archivo o proceso.                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| fileName                                  | Disponible si entityType es *File*.<br>El nombre de archivo de las alertas asociadas a un archivo o proceso                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| Rutaarchivo                                  | Disponible si entityType es *File*.<br>La ruta de acceso del archivo para las alertas asociadas a un archivo o proceso                                                                                                                                                                                                                                                                                    | C: \\ \\ \\ \\ \_ trabajo \\ \\ \_ del agente Temp \\ \\ deploy \_ sistema 2020-09-06 12 \_ 14 54 de \_ \\ \\ salida                                                                                                                                                                    |
| Idproceso                                 | Disponible si entityType es *Process*.                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | Disponible si entityType es *Process*.                                                                                                                                                                                                                                                                                                                                                     | " \\ " El archivo está listo para descargar \_1911150169.exe\\ ""                                                                                                                                                                                           |
| processCreationTime                       | Disponible si entityType es *Process*.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T03:25:38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | Disponible si entityType es *Process*.                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | Disponible si entityType es *Process*.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T02:12:32.8616797 Z                                                                                                                                                                                                                      |
| ipAddress                                 | Disponible si entityType es *IP*. <br>Dirección IP de alertas asociadas con eventos de red, como *la comunicación a un destino de red malintencionado*.                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| URL                                       | Disponible si entityType es *URL*. <br>Dirección URL de las alertas asociadas a eventos de red, como *la comunicación a un destino de red malintencionado*.                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| accountName                               | Disponible si entityType es *User*.                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| domainName                                | Disponible si entityType es *User*.                                                                                                                                                                                                                                                                                                                                                        | Europa. Corp. contoso                                                                                                                                                                                                                              |
| userSid                                   | Disponible si entityType es *User*.                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | Disponible si entityType es *User*.                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | Disponible si entityType es *User* / MailMessage de *buzón* de usuario / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | Disponible si entityType es *MailBox*.                                                                                                                                                                                                                                                                                                                                                     | prueba user2                                                                                                                                                                                                                                        |
| mailboxAddress                            | Disponible si entityType es *User* / MailMessage de *buzón* de usuario / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | Disponible si entityType es  *MailCluster*.                                                                                                                                                                                                                                                                                                                                                 | Titular P2SenderDomain; ContentType                                                                                                                                                                                                                |
| sender                                    | Disponible si entityType es *User* / MailMessage de *buzón* de usuario / *MailMessage*.                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| destinatario                                 | Disponible si entityType es *MailMessage*.                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| subject                                   | Disponible si entityType es *MailMessage*.                                                                                                                                                                                                                                                                                                                                                 | \[\]Atención externa                                                                                                                                                                                                                            |
| deliveryAction                            | Disponible si entityType es *MailMessage*.                                                                                                                                                                                                                                                                                                                                                 | Pronuncia                                                                                                                                                                                                                                         |
| securityGroupId                           | Disponible si entityType es  *SecurityGroup*.                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-ab09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | Disponible si entityType es  *SecurityGroup*.                                                                                                                                                                                                                                                                                                                                               | Operadores de configuración de red                                                                                                                                                                                                                   |
| registryHive                              | Disponible si entityType es  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | HKEY \_ local \_ Machine                                                                                                                                                                                                                              |
| Deleteinstance                               | Disponible si entityType es  *Registry*.                                                                                                                                                                                                                                                                                                                                                     | SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | Disponible si entityType es  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | Cadena                                                                                                                                                                                                                                            |
| Deleteinstance                             | Disponible si entityType es  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | IDENTIFICADOR, si existe, del dispositivo relacionado con la entidad.                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>Ejemplo

**Solicitud**

```
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

## <a name="related-topic"></a>Tema relacionado
- [API de incidentes](api-incident.md)
- [Incidente de actualización](api-update-incidents.md)
