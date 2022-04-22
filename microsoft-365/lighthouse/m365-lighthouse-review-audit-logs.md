---
title: Revisión de los registros de auditoría en Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo revisar los registros de auditoría.
ms.openlocfilehash: ca4d1e9941e0c15fee169def7be0c2d801f522c2
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "65022853"
---
# <a name="review-audit-logs-in-microsoft-365-lighthouse"></a>Revisión de los registros de auditoría en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse las acciones de registro de registros de auditoría que generan un cambio en Lighthouse u otros servicios de Microsoft 365. Crear, editar, eliminar, asignar y acciones remotas crean eventos de auditoría que puede revisar. La auditoría está habilitada de forma predeterminada para todos los clientes. No se puede deshabilitar.

## <a name="before-you-begin"></a>Antes de empezar

Para ver los registros de auditoría, debe tener uno de los permisos siguientes:

- rol de Azure Active Directory (Azure AD): administrador global del inquilino del asociado

- Rol del Centro de partners de Microsoft: Agente de administración

## <a name="review-audit-logs"></a>Revisión de los registros de auditoría

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Registros de auditoría**.

    > [!NOTE]
    > Puede tardar hasta 1 hora en ver nuevos registros. Vaya al servicio correspondiente para ver los cambios más recientes.

2. Filtre los registros, según sea necesario, mediante las siguientes opciones:

    - **Intervalo de fechas** : mes, semana o día anteriores.
    - **Inquilinos: etiquetas** de inquilino o nombres de inquilino de cliente.
    - **Actividad**: Microsoft 365 tipo de actividad que corresponde a la acción realizada. Para obtener más información, vea la tabla [Actividades](#activities) .
    - **Iniciado por** : Quién inició la acción.

3. Seleccione un registro de la lista para ver los detalles completos, incluido el cuerpo **de la solicitud** .

    Para exportar datos de registro a un archivo de valores separados por comas (.csv), seleccione **Exportar**.

## <a name="activities"></a>Actividades

En la tabla siguiente se enumeran las actividades capturadas en los registros de auditoría de Lighthouse. La lista está sujeta a cambios a medida que se crean nuevas acciones. Puede usar la actividad que aparece en el registro de auditoría para ver qué acción se inició.<br><br>

| Nombre de la actividad | Área en Lighthouse | Acción iniciada | Servicio afectado |
|--|--|--|--|
| **aplicar** o **implementar** | Espacios empresariales | Aplicación de un plan de implementación | Azure AD, Microsoft Endpoint Manager (MEM) |
| **assignTag** | Espacios empresariales | Aplicación de una etiqueta desde un cliente | Faro |
| **changeDeploymentStatus** o **assign** | Espacios empresariales | Actualización del estado del plan de acción para el plan de implementación | Faro |
| **managedTenantOperations** | Espacios empresariales | Visualización de información sobre un plan de implementación | Azure AD |
| **offboardTenant** | Espacios empresariales | Inactivar un cliente | Faro |
| **resetTenantOnboardingStatus** | Espacios empresariales | Reactivación de un cliente | Faro |
| **tenantTags** | Espacios empresariales | Creación o eliminación de una etiqueta | Faro |
| **tenantCustomizedInformation** | Espacios empresariales | Creación, actualización o eliminación de un sitio web de cliente o información de contacto | Faro |
| **unassignTag** | Espacios empresariales | Quitar una etiqueta de un cliente | Faro |
| **Validar** | Espacios empresariales | Prueba de un plan de implementación | Azure AD |
| **blockUserSignin** | Usuarios | Bloquear inicio de sesión | Azure AD |
| **confirmUsersCompromised** | Usuarios | Confirmación de que un usuario está en peligro | Azure AD |
| **dismissUsersRisk** | Usuarios | Descartar el riesgo del usuario | Azure AD |
| **resetUserPassword** | Usuarios | Restablecer contraseña | Azure AD |
| **getConditionalAccessPolicies** | Usuarios | Visualización de directivas de CA que requieren MFA | Azure AD |
| **getTenantIDToTenantNameMap** | Usuarios | Búsqueda de identificadores | Azure AD |
| **getUsers** | Usuarios | Búsqueda de usuarios | Azure AD |
| **getUsersWithoutMfa** | Usuarios | Visualización de usuarios no registrados para MFA | Azure AD |
| **getSsprEnabledButNotRegisteredUsers** | Usuarios | Visualización de usuarios no registrados para SSPR | Azure AD |
| **setCustomerSecurityDefaultsEnabledStatus** | Usuarios | Habilitación de la autenticación multifactor (MFA) con valores predeterminados de seguridad | Azure AD |
|**getCompliancePolicyInfo** | Dispositivos | Visualización de una directiva | MEM
|**getDeviceCompliancePolicyStates** | Dispositivos | Visualización de los estados de directiva | MEM
|**getDeviceCompliancePolicySettingStates** | Dispositivos | Visualización de la configuración no compatible | MEM
|**getDeviceCompliancePolicySettingStateSummaries** | Dispositivos | Visualización de dispositivos no compatibles | MEM
|**getTenantsDeviceCompliancePolicies** | Dispositivos | Comparación de directivas | MEM
| **restartDevice** | Dispositivos | Restart | MEM |
| **syncDevice** | Dispositivos | Sincronizar | MEM |
| **rebootNow** | Administración de amenazas | Reiniciar | MEM |
| **reprovision** | Windows 365 | Reintentar el aprovisionamiento | Windows 365 |
| **getDeviceUserInfo** | Administración de amenazas | Visualización de la información de usuario del dispositivo administrado  | MEM |
| **getManagedDevice**, **remoteActionAudits** o **deviceActionResults** | Administración de amenazas | Visualización de la información del dispositivo administrado  | MEM |
| **windowsDefenderScanFull** | Administración de amenazas | Examen completo | MEM |
| **windowsDefenderScan** | Administración de amenazas | Examen rápido | MEM |
| **windowsDefenderUpdateSignatures** | Administración de amenazas | Actualización del antivirus | MEM |

## <a name="next-steps"></a>Siguientes pasos

Si necesita más información, use Microsoft Graph API para acceder a más eventos de auditoría. Para obtener más información, consulte [Información general sobre la administración multiinquilino mediante la API de Microsoft 365 Lighthouse](/graph/managedtenants-concept-overview).

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)
