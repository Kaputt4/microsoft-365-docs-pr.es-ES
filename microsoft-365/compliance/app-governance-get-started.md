---
title: Introducción a la gobernanza de aplicaciones
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Introducción a las funcionalidades de gobernanza de aplicaciones para controlar sus aplicaciones.
ms.openlocfilehash: c4cdc83d41a888fbf395d2c13e442bbaaf7da54e
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "53621684"
---
# <a name="get-started-with-app-governance-in-preview"></a>Introducción a la gobernanza de aplicaciones (en versión preliminar)

Para empezar a usar el complemento de gobernanza de aplicaciones para Microsoft Cloud App Security:

1. Compruebe que su cuenta tenga el [nivel de licencias adecuado](#licensing-for-app-governance). La gobernanza de aplicaciones es una característica complementaria para Microsoft Cloud App Security (MCAS) y, por tanto, MCAS debe estar presente en su cuenta como un producto independiente o como parte de los distintos paquetes de licencia que se enumeran a continuación.
1. Debe tener uno de los [roles de administrador](#administrator-roles) que se enumeran a continuación para acceder a las páginas de gobernanza de la aplicación en el portal.
1. El registro de espacios empresariales de su organización debe estar dentro de una de las [áreas admitidas de Norteamérica, Europa o África](app-governance-countries.md).

## <a name="add-app-governance-to-your-microsoft-365-account"></a>Incorpore la gobernanza de aplicaciones a su cuenta de Microsoft 365

Para los clientes nuevos de Microsoft 365:

1. En la parte superior de esta página, haga clic en el botón  **Cuenta gratuita** .
1. En  **Probar Microsoft 365 para empresas**  haga clic en  **Probar 1 mes gratis**.
1. Complete los pasos para el registro.

Para los clientes existentes de Microsoft 365:

1. En el Centro de administración de Microsoft 365, vaya a  **Facturación** > **Servicios de compra**  y haga clic en  **Complementos**. Use la barra de búsqueda para buscar **Gobernanza de aplicaciones**.
1. En la tarjeta de gobernanza de aplicaciones, haga clic en  **Detalles**.
1. Haga clic en  **Activar el inicio de la prueba gratuita**.

## <a name="add-integration-with-mcas"></a>Incorporación de la integración con MCAS 

Requisitos previos:

- Office 365 está conectado en Cloud App Security
- Las aplicaciones de Microsoft Office 365 Azure AD están habilitadas

Para habilitar la sincronización de gobernanza de aplicaciones con Cloud App Security siga estos pasos:

1. Vaya al portal de Microsoft Cloud App Security: [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)
1. Haga clic en el icono de engranaje (esquina superior derecha) y seleccione **Configuración**.
1. En **Protección contra amenazas**, seleccione **Gobernanza de aplicaciones**.
1. Haga clic en **Habilitar la integración de Gobernanza de aplicaciones** y, a continuación, seleccione **Guardar**.

A continuación, revise las directivas recién habilitadas en MCAS. Las nuevas directivas pueden tardar unos minutos en aparecer una vez habilitada la integración.

- Reputación de la aplicación de OAuth Microsoft 365
- Microsoft 365 detección de suplantación de identidad (phishing) de OAuth
- Microsoft 365 gobernanza de aplicaciones de OAuth
- Revisión del widget de gobernanza de aplicaciones en el panel de MCAS
- Revisión de las alertas de gobernanza de aplicaciones recién generadas en las alertas de MCAS
- Revisión de las directivas de MCAS M365 OAuth en la lista de directivas de gobernanza de aplicaciones
- Revisión de las alertas de OAuth de MCAS M365 recién generadas en las alertas de gobernanza de aplicaciones

## <a name="licensing-for-app-governance"></a>Licencias para la gobernanza de aplicaciones

Antes de empezar a trabajar con la gobernanza de aplicaciones, debería confirmar [Centro de administración de Microsoft 365: suscripciones](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/subscriptions) y los complementos. Para obtener acceso y usar la gobernanza de aplicaciones, su organización debe tener una de las siguientes suscripciones:

- Microsoft Cloud App Security
- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Microsoft 365 E5 Developer (sin Windows ni audioconferencia)
- Gobierno y protección de información de Microsoft 365 E5
- Seguridad de Microsoft 365 E5
- Microsoft 365 E5 con minutos de llamada
- Microsoft 365 E5 sin audioconferencia
- Cumplimiento de Microsoft 365 A5 para profesores
- Cumplimiento de Microsoft 365 A5 para estudiantes
- Microsoft 365 A5 para profesores
- Microsoft 365 A5 para estudiantes
- Gobierno y protección de información de Microsoft 365 A5 para profesores
- Gobierno y protección de información de Microsoft 365 A5 para estudiantes
- Seguridad de Microsoft 365 A5 para profesores
- Seguridad de Microsoft 365 A5 para estudiantes
- Ventajas de uso para estudiantes de Microsoft 365 A5
- Microsoft 365 A5 con minutos de llamada para profesores
- Microsoft 365 A5 con minutos de llamada para estudiantes
- Microsoft 365 A5 sin audioconferencia para profesores
- Microsoft 365 A5 sin audioconferencia para estudiantes
- Ventajas de uso de Microsoft 365 A5 sin audioconferencia para estudiantes

## <a name="administrator-roles"></a>Roles de administrador

> [!NOTE]
> Solo el rol de administrador global puede activar la prueba gratuita de gobernanza de aplicaciones.

Se requiere uno de los siguientes roles de administrador para ver las páginas de gobernanza de aplicaciones o administrar las directivas y la configuración:

- Administrador de la aplicación
- Administrador de aplicaciones en la nube
- Administrador de la empresa
- Administrador de cumplimiento
- Administrador de datos de cumplimiento
- Lector de cumplimiento (solo lectura)
- Lector global
- Administrador de seguridad
- Operador de seguridad
- Lector de seguridad (solo lectura)

> [!NOTE]
> Solo un administrador global puede activar la evaluación gratuita de gobernanza de aplicaciones.

Estas son las funcionalidades de cada rol.

| Rol | Leer del panel | Leer todas las aplicaciones |Leer directivas | Crear, actualizar o eliminar directivas | Leer alertas | Actualizar alertas | Leer la configuración | Actualizar configuración | Leer corrección | Actualizar corrección |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| Administrador de la aplicación | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Administrador de aplicaciones en la nube | ![Marca de verificación](..\media\checkmark.png) | | | | | | | | | |
| Administrador de la empresa | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Administrador de cumplimiento | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Administrador de datos de cumplimiento | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Lector de cumplimiento | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | | |
| Lector global  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | | |
| Administrador de seguridad | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Operador de seguridad | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Lector de seguridad  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | |
|||||||||| | |

Para obtener información adicional acerca de cada rol, consulte[permisos de rol de administrador](/azure/active-directory/roles/permissions-reference).

## <a name="canceling-your-trial"></a>Para cancelar la versión de prueba

Si no ha participado en la versión preliminar privada y desea cancelar la versión de prueba de gobernanza de aplicaciones, puede comunicarse con el contacto de CXE o seguir estos pasos:

1. En el Centro de administración de Microsoft 365, vaya a **Facturación** > **Sus productos**.
1. Vaya a la prueba de gobernanza de aplicaciones, haga clic en los tres puntos y seleccione **Cancelar suscripción**.
1. En el panel flotante resultante, proporcione un motivo para la cancelación, cualquier comentario adicional y seleccione **Cancelar suscripción**.
1. Seleccione **Cancelar suscripción** en la pantalla emergente resultante. La versión de prueba se ha cancelado, perderá el acceso a la gobernanza de aplicaciones y se eliminarán los datos de gobernanza de aplicaciones (datos de registro que se usan para crear la información y detecciones de gobernanza de aplicaciones; ningún correo electrónico ni otros archivos se verán afectados).

## <a name="known-issues-for-the-public-preview"></a>Problemas conocidos para esta versión preliminar pública.

El equipo de gobernanza de aplicaciones ha identificado los siguientes problemas conocidos de la versión preliminar: 

- Sincronización bidireccional entre Microsoft Defender y las alertas de gobernanza de aplicaciones. Ahora las alertas resueltas en Defender también tendrán que resolverse manualmente en la gobernanza de aplicaciones.
- La información de las cuentas prioritarias en las pestañas Usuarios de la aplicación y Uso no funcionará según lo esperado para determinados usuarios.
