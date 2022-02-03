---
title: Revisar registros de auditoría
f1.keywords: NOCSH
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo revisar los registros de auditoría.
ms.openlocfilehash: a2c9efe88930ad0aae197a5cac26cf06b1386a53
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62354941"
---
# <a name="review-audit-logs"></a>Revisar registros de auditoría

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplan los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, consulte [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse auditoría registra las acciones que generan un cambio en Lighthouse u otros Microsoft 365 servicios. Crear, editar, eliminar, asignar y acciones remotas crean eventos de auditoría que puede revisar. La auditoría está habilitada de forma predeterminada para todos los clientes. No se puede deshabilitar.

## <a name="before-you-begin"></a>Antes de empezar

Para ver los registros de auditoría, debe tener uno de los siguientes permisos:

- Azure AD de usuario: administrador global del espacio empresarial asociado

- Rol del Centro de partners: agente de administración

## <a name="review-logs"></a>Revisar registros

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Registros de auditoría**.

    > [!NOTE]
    > Es posible que tarde hasta 1 hora en ver nuevos registros. Vaya al servicio correspondiente para ver los cambios más recientes.

2. Para filtrar los registros, refine la lista con las siguientes opciones:

    - **Intervalo de fechas** : mes anterior, semana o día.
    - **Inquilinos: etiquetas** de inquilino o nombres de inquilino de cliente.
    - **Actividad**: Microsoft 365 de actividad que corresponde a la acción realizada. Para obtener más información, vea tabla Tipos de actividad.
    - **Iniciado por**: Quién inició la acción.

3. Seleccione un registro de la lista para ver detalles completos, incluido el **cuerpo de la** solicitud.

Seleccione **Exportar** para exportar datos de registro a un archivo de valores separados por comas (.csv).

## <a name="activity-types"></a>Tipos de actividad

La siguiente tabla es una lista de tipos de actividad capturados en los registros de auditoría de Lighthouse. La lista está sujeta a cambios a medida que se crean nuevas acciones. Puede usar el valor de actividad del registro de auditoría para ver qué acción se inició.

| Nombre de la actividad    | Área en Microsoft 365 Lighthouse | Acción iniciada  | Servicio afectado           |
|------------------|----------------------------------|-------------------|----------------------------|
|**aplicar**                                   | Espacios empresariales                          | Aplicar plan de implementación                                           | Azure AD, Microsoft Endpoint Manager                   |
|**assignTag**                                | Espacios empresariales                          | Aplicar una etiqueta desde un cliente                                      | Microsoft 365 Lighthouse   |
|**changeDeploymentStatus**                   | Espacios empresariales                          | Estado del plan de acción para el plan de implementación                        | Microsoft 365 Lighthouse   |
|**offboardTenant**                            | Espacios empresariales                          | Inactivar un cliente                                          | Microsoft 365 Lighthouse   |
|**resetTenantOnboardingStatus**              | Espacios empresariales                          | Reactivar un cliente                                              | Microsoft 365 Lighthouse   |
|**tenantTags**                               | Espacios empresariales                          | Crear o eliminar una etiqueta                                           | Microsoft 365 Lighthouse   |
|**tenantCustomizedInformation**              | Espacios empresariales                          | Crear, actualizar o eliminar información de contacto o sitio web del cliente | Microsoft 365 Lighthouse   |
|**unassignTag**                              | Espacios empresariales                          | Quitar una etiqueta de un cliente                                    | Microsoft 365 Lighthouse   |
| **blockUserSignin**                          | Usuarios                            | Bloquear inicio de sesión                                                     | Azure AD                   |
| **confirmUsersCompromised**                  | Usuarios                            | Confirmar que el usuario está en peligro                                        | Azure AD                   |
| **dismissUsersRisk**                         | Usuarios                            | Descartar riesgo de usuario                                                | Azure AD                   |
| **resetUserPassword**                        | Usuarios                            | Restablecer contraseña                                                   | Azure AD                   |
| **setCustomerSecurityDefaultsEnabledStatus** | Usuarios                            | Habilitar MFA con valores predeterminados de seguridad                               | Azure AD                   |
|**restartDevice**                            | Dispositivos                          | Restart                                                          | Microsoft Endpoint Manager |
| **syncDevice**                               | Dispositivos                          | Sincronizar                                                             | Microsoft Endpoint Manager |
| **rebootNow**                                | Administración de amenazas                | Reiniciar                                                           | Microsoft Endpoint Manager |
| **reprovision**                              | Espacios empresariales                          | Aprovisionamiento de reintentos                                               | Windows 365                |
| **windowsDefenderScanFull**                  | Administración de amenazas                | Examen completo                                                       | Microsoft Endpoint Manager |
| **windowsDefenderScan**                      | Administración de amenazas                | Examen rápido                                                       | Microsoft Endpoint Manager |
| **windowsDefenderUpdateSignatures**          | Administración de amenazas                | Actualizar antivirus                                                | Microsoft Endpoint Manager |

## <a name="next-steps"></a>Siguientes pasos

Si necesita más información, puede usar la API de Microsoft Graph para obtener acceso a más eventos de auditoría. Para obtener más información, vea [Overview for multi-tenant management using the Microsoft 365 Lighthouse API](/graph/managedtenants-concept-overview).

## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
