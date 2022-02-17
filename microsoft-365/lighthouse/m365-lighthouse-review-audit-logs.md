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
ms.openlocfilehash: 69eb057c0b6a7daf835ec613b7d386e1a7fbfbaa
ms.sourcegitcommit: 6e43aeff217afe97876137b1ead8df26db6e9937
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "62859246"
---
# <a name="review-audit-logs"></a>Revisar registros de auditoría

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplan los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, consulte [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse auditoría registra las acciones que generan un cambio en Lighthouse u otros Microsoft 365 servicios. Crear, editar, eliminar, asignar y acciones remotas crean eventos de auditoría que puede revisar. La auditoría está habilitada de forma predeterminada para todos los clientes. No se puede deshabilitar.

## <a name="before-you-begin"></a>Antes de empezar

Para ver los registros de auditoría, debe tener uno de los siguientes permisos:

- Azure Active Directory (Azure AD): administrador global del espacio empresarial asociado

- Rol del Centro de partners de Microsoft: agente de administración

## <a name="review-audit-logs"></a>Revisar registros de auditoría

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Registros de auditoría**.

    > [!NOTE]
    > Es posible que tarde hasta 1 hora en ver nuevos registros. Vaya al servicio correspondiente para ver los cambios más recientes.

2. Filtre los registros, según sea necesario, mediante las siguientes opciones:

    - **Intervalo de fechas** : mes anterior, semana o día.
    - **Inquilinos: etiquetas** de inquilino o nombres de inquilino de cliente.
    - **Actividad**: Microsoft 365 de actividad que corresponde a la acción realizada. Para obtener más información, consulte la [tabla](#activities) Actividades.
    - **Iniciado por**: Quién inició la acción.

3. Seleccione un registro de la lista para ver todos los detalles, incluido el **cuerpo de la** solicitud.

    Para exportar datos de registro a un archivo de valores separados por comas (.csv), seleccione **Exportar**.

## <a name="activities"></a>Actividades

En la tabla siguiente se enumeran las actividades capturadas en los registros de auditoría de Lighthouse. La lista está sujeta a cambios a medida que se crean nuevas acciones. Puede usar la actividad que aparece en el registro de auditoría para ver qué acción se inició.<br><br>

| Nombre de la actividad | Área de Faro | Acción iniciada | Servicio afectado |
|--|--|--|--|
| **aplicar** | Espacios empresariales | Aplicar plan de implementación | Azure AD, Microsoft Endpoint Manager (MEM) |
| **assignTag** | Espacios empresariales | Aplicar una etiqueta desde un cliente | Faro |
| **changeDeploymentStatus** | Espacios empresariales | Estado del plan de acción para el plan de implementación | Faro |
| **offboardTenant** | Espacios empresariales | Inactivar un cliente | Faro |
| **resetTenantOnboardingStatus** | Espacios empresariales | Reactivar un cliente | Faro |
| **tenantTags** | Espacios empresariales | Crear o eliminar una etiqueta | Faro |
| **tenantCustomizedInformation** | Espacios empresariales | Crear, actualizar o eliminar un sitio web de cliente o información de contacto | Faro |
| **unassignTag** | Espacios empresariales | Quitar una etiqueta de un cliente | Faro |
| **blockUserSignin** | Usuarios | Bloquear inicio de sesión | Azure AD |
| **confirmUsersCompromised** | Usuarios | Confirmar que un usuario está en peligro | Azure AD |
| **dismissUsersRisk** | Usuarios | Descartar riesgo de usuario | Azure AD |
| **resetUserPassword** | Usuarios | Restablecer contraseña | Azure AD |
| **setCustomerSecurityDefaultsEnabledStatus** | Usuarios | Habilitar la autenticación multifactor (MFA) con valores predeterminados de seguridad | Azure AD |
| **restartDevice** | Dispositivos | Restart | MEM |
| **syncDevice** | Dispositivos | Sincronizar | MEM |
| **rebootNow** | Administración de amenazas | Reiniciar | MEM |
| **reprovision** | Windows 365 | Aprovisionamiento de reintentos | Windows 365 |
| **windowsDefenderScanFull** | Administración de amenazas | Examen completo | MEM |
| **windowsDefenderScan** | Administración de amenazas | Examen rápido | MEM |
| **windowsDefenderUpdateSignatures** | Administración de amenazas | Actualizar antivirus | MEM |

## <a name="next-steps"></a>Pasos siguientes

Si necesita más información, use la API de Microsoft Graph para obtener acceso a más eventos de auditoría. Para obtener más información, vea [Overview for multi-tenant management using the Microsoft 365 Lighthouse API](/graph/managedtenants-concept-overview).

## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
