---
title: Introducción a la administración de privacidad de Microsoft (versión preliminar)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo configurar la administración de privacidad para su organización, establecer roles y permisos y configurar opciones importantes.
ms.openlocfilehash: 1472b20b32315480f5b7b237ca91a465de293747
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58247531"
---
# <a name="get-started-with-privacy-management-preview"></a>Introducción a la administración de privacidad (versión preliminar)

En este artículo: obtenga  información sobre cómo configurar el  acceso a la administración de privacidad de su organización, cómo empezar a evaluar los datos y cómo controlar la configuración **importante.**

## <a name="who-can-access-privacy-management"></a>Quién acceso a la administración de privacidad

La versión preliminar pública de la administración de privacidad está disponible en el Centro de cumplimiento de Microsoft 365 y está disponible para las organizaciones con licencias empresariales E1, E3 y E5 en Office 365 y Microsoft 365. Cuando la administración de privacidad pasa a la disponibilidad general, las organizaciones que usaron la versión preliminar pública tendrán que obtener una nueva licencia.

Para una guía detallada sobre las licencias, vea: [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

> [!Note]
> La versión preliminar pública de la administración de privacidad no estará disponible para los clientes Community (GCC) del Departamento de Defensa (DoD) moderados, GCC altos o del Departamento de Defensa.

## <a name="set-up-privacy-management"></a>Configurar la administración de privacidad

Para empezar con la administración de privacidad, primero obtén la licencia de prueba e inicia sesión. A continuación, puede asignar permisos a los usuarios y revisar la configuración.

### <a name="get-trial-license"></a>Obtener licencia de prueba

Para empezar con la vista previa pública, el administrador global puede obtener la licencia de prueba de administración de privacidad gratuita del [Centro de administración.](https://aka.ms/purchasem365privacy) Seleccione "Iniciar prueba" para comenzar. La licencia dura un mes y puede renovarla sin costo según sea necesario durante la versión preliminar pública.

Después de obtener la suscripción, espere hasta 30 minutos para que se active. A continuación, vuelva a la administración de privacidad para empezar. Se le pedirá que confirme que está de acuerdo con los términos y el proceso de evaluación de datos personales ([más información](privacy-management.md#how-we-evaluate-your-data)). Puede revisar los vínculos proporcionados en su totalidad antes de continuar. Una vez que acepte, puede tardar hasta 24 horas antes de que la administración de privacidad comience a proporcionar información sobre los datos de su organización.

Si no tienes el rol necesario para obtener la suscripción o el consentimiento a los términos de uso de la administración de privacidad, se te pedirá que te contactes con el administrador global para obtener ayuda.

### <a name="set-user-permissions-and-assign-roles"></a>Establecer permisos de usuario y asignar roles

La administración de privacidad usa un modelo de permisos de control de acceso basado en roles (RBAC). Solo los usuarios a los que se asigna un rol pueden acceder a la administración de privacidad y las acciones permitidas por cada usuario están restringidas por tipo de función.

Se recomienda que el administrador global inicie sesión y establezca los permisos de usuario en el Centro de cumplimiento cuando use la administración de privacidad por primera vez. Para un inicio rápido, el grupo de roles De administración de privacidad tiene permisos para tener acceso a todas las características de la administración de privacidad. Este grupo puede ser un buen ajuste para las organizaciones donde la misma persona puede realizar todas las tareas dentro de la solución de administración de privacidad. Otros roles de privacidad le permiten tomar un control más detallado y asignar usuarios a funciones o características seleccionadas.

Para obtener más información sobre los grupos de roles y cómo conceder acceso, vea [Set user permissions and assign roles](privacy-management-permissions.md).

### <a name="manage-settings"></a>Administrar la configuración

Se puede Configuración la página a través del engranaje de la esquina superior derecha de las páginas principales de la administración de privacidad. Permite a los administradores de administración de privacidad configurar propiedades esenciales en la administración de privacidad.

Es posible que desee revisar la configuración predeterminada y realizar los ajustes deseados antes de comenzar. Para obtener más información sobre sus opciones, vea [Administrar la configuración de administración de privacidad.](privacy-management-settings.md)

## <a name="get-initial-data-insights"></a>Obtener información de datos inicial

Después de iniciar sesión en la administración de privacidad, llegarás a la página **Información** general. Esta página proporciona información sobre los datos personales almacenados en su entorno de Microsoft 365 con el fin de ayudarle a detectar rápidamente problemas, identificar indicadores de riesgo y tomar medidas para solucionar problemas. Su información general debe rellenarse con información inicial en las primeras 24 horas de registrarse. A medida que siga usando la administración de privacidad, la página de información general se actualizará para continuar con la información actual.

Para obtener más información sobre los  datos a lo largo del tiempo, la página perfil de datos proporcionará más visualizaciones y análisis y le proporcionará una vista de alto nivel de los datos de su organización por ubicación geográfica y por Microsoft 365 servicio.

Para obtener más información sobre estas páginas, vea [Buscar y visualizar los datos](privacy-management-data-profile.md).

## <a name="get-started-with-default-policies"></a>Introducción a las directivas predeterminadas 

La administración de privacidad ayudará a iniciar el proceso de evaluación de datos creando tres directivas con la configuración predeterminada, usando las plantillas para la minimización de datos, la sobreexposición de datos y las transferencias de datos. Estas directivas estarán activas de forma predeterminada, pero no desencadenarán automáticamente los mensajes de notificación ni los mensajes de corrección. Después de la configuración inicial, puede continuar con la creación y personalización de sus propias directivas. Para obtener más información, vea [Create and manage policies](privacy-management-policies.md).
