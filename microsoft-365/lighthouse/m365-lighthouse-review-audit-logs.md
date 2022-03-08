---
title: Revisar registros de auditoría
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
description: Para proveedores de servicios administrados (MSP) con Microsoft 365 Lighthouse, obtenga información sobre cómo revisar los registros de auditoría.
ms.openlocfilehash: e16f6eb83d1fdc9f5aea2fdc6463959cc07e5650
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329451"
---
# <a name="review-audit-logs"></a>Revisar registros de auditoría

La auditoría de Faro de Microsoft 365 registra acciones de registro que generan un cambio en Lighthouse u otros servicios de Microsoft 365. Crear, editar, eliminar, asignar y acciones remotas crean eventos de auditoría que puede revisar. La auditoría está habilitada de forma predeterminada para todos los clientes. No se puede deshabilitar.

## <a name="before-you-begin"></a>Antes de empezar

Para ver los registros de auditoría, debe tener uno de los siguientes permisos:

- Rol Azure Active Directory (Azure AD): administrador global del inquilino de partners

- Rol centro de partners de Microsoft: agente de administración

## <a name="review-audit-logs"></a>Revisar registros de auditoría

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Registros de auditoría**.

    > [!NOTE]
    > Es posible que tarde hasta 1 hora en ver nuevos registros. Vaya al servicio correspondiente para ver los cambios más recientes.

2. Filtre los registros, según sea necesario, mediante las siguientes opciones:

    - **Intervalo de fechas** : mes anterior, semana o día.
    - **Inquilinos: etiquetas** de inquilino o nombres de inquilino de cliente.
    - **Actividad** : tipo de actividad de Microsoft 365 que corresponde a la acción realizada. Para obtener más información, consulte la [tabla](#activities) Actividades.
    - **Iniciado por** : quién inició la acción.

3. Seleccione un registro de la lista para ver todos los detalles, incluido el **cuerpo de la** solicitud.

    Para exportar datos de registro a un archivo de valores separados por comas (.csv), seleccione **Exportar**.

## <a name="activities"></a>Actividades

En la tabla siguiente se enumeran las actividades capturadas en los registros de auditoría de Lighthouse. La lista está sujeta a cambios a medida que se crean nuevas acciones. Puede usar la actividad que aparece en el registro de auditoría para ver qué acción se inició.<br><br>

| Nombre de la actividad | Área de Faro | Acción iniciada | Servicio afectado |
|--|--|--|--|
| **aplicar** o **implementar** | Espacios empresariales | Aplicar un plan de implementación | Azure AD, Microsoft Endpoint Manager (MEM) |
| **assignTag** | Espacios empresariales | Aplicar una etiqueta desde un cliente | Faro |
| **changeDeploymentStatus** o **assign** | Espacios empresariales | Actualizar el estado del plan de acción para el plan de implementación | Faro |
| **managedTenantOperations** | Espacios empresariales | Ver información sobre un plan de implementación | Azure AD |
| **offboardTenant** | Espacios empresariales | Inactivar un cliente | Faro |
| **resetTenantOnboardingStatus** | Espacios empresariales | Reactivar un cliente | Faro |
| **tenantTags** | Espacios empresariales | Crear o eliminar una etiqueta | Faro |
| **tenantCustomizedInformation** | Espacios empresariales | Crear, actualizar o eliminar un sitio web de cliente o información de contacto | Faro |
| **unassignTag** | Espacios empresariales | Quitar una etiqueta de un cliente | Faro |
| **validar** | Espacios empresariales | Probar un plan de implementación | Azure AD |
| **blockUserSignin** | Usuarios | Bloquear inicio de sesión | Azure AD |
| **confirmUsersCompromised** | Usuarios | Confirmar que un usuario está en peligro | Azure AD |
| **dismissUsersRisk** | Usuarios | Descartar riesgo de usuario | Azure AD |
| **resetUserPassword** | Usuarios | Restablecer contraseña | Azure AD |
| **getConditionalAccessPolicies** | Usuarios | Ver directivas de CA que requieren MFA | Azure AD |
| **getTenantIDToTenantNameMap** | Usuarios | Buscar los IDs | Azure AD |
| **getUsers** | Usuarios | Buscar usuarios | Azure AD |
| **getUsersWithoutMfa** | Usuarios | Ver usuarios no registrados para MFA | Azure AD |
| **getSsprEnabledButNotRegisteredUsers** | Usuarios | Ver usuarios no registrados para SSPR | Azure AD |
| **setCustomerSecurityDefaultsEnabledStatus** | Usuarios | Habilitar la autenticación multifactor (MFA) con valores predeterminados de seguridad | Azure AD |
|**getCompliancePolicyInfo** | Dispositivos | Ver una directiva | MEM
|**getDeviceCompliancePolicyStates** | Dispositivos | Ver estados de directiva | MEM
|**getDeviceCompliancePolicySettingStates** | Dispositivos | Ver la configuración no compatible | MEM
|**getDeviceCompliancePolicySettingStateSummaries** | Dispositivos | Ver dispositivos no compatibles | MEM
|**getTenantsDeviceCompliancePolicies** | Dispositivos | Comparar directivas | MEM
| **restartDevice** | Dispositivos | Restart | MEM |
| **syncDevice** | Dispositivos | Sincronizar | MEM |
| **rebootNow** | Administración de amenazas | Reiniciar | MEM |
| **reprovision** | Windows 365 | Aprovisionamiento de reintentos | Windows 365 |
| **getDeviceUserInfo** | Administración de amenazas | Ver información de usuario de dispositivo administrado  | MEM |
| **getManagedDevice**, **remoteActionAudits** o **deviceActionResults** | Administración de amenazas | Ver información de dispositivo administrado  | MEM |
| **windowsDefenderScanFull** | Administración de amenazas | Examen completo | MEM |
| **windowsDefenderScan** | Administración de amenazas | Examen rápido | MEM |
| **windowsDefenderUpdateSignatures** | Administración de amenazas | Actualizar antivirus | MEM |

## <a name="next-steps"></a>Pasos siguientes

Si necesita más información, use la API de Microsoft Graph para obtener acceso a más eventos de auditoría. Para obtener más información, vea [Overview for multi-tenant management using the Microsoft 365 Lighthouse API](/graph/managedtenants-concept-overview).

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes sobre el faro de Microsoft 365](m365-lighthouse-faq.yml) (artículo)
