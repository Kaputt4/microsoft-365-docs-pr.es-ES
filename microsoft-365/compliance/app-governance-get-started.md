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
ms.custom: admindeeplinkMAC
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Introducción a las funcionalidades de gobernanza de aplicaciones para controlar sus aplicaciones.
ms.openlocfilehash: 74a9a9ad29e9d99740500d7dd249fd69cbbc6547
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189578"
---
# <a name="get-started-with-app-governance-in-preview"></a>Introducción a la gobernanza de aplicaciones (en versión preliminar)

[![Registrarse para la prueba gratuita de la gobernanza de aplicaciones](../media/manage-app-protection-governance/large-app-governance-banner.png)](https://admin.microsoft.com/Commerce/Trial.aspx?OfferId=20be85b6-b196-402c-82b4-36b4e72862dc)

Para empezar a usar el complemento de gobernanza de aplicaciones para Microsoft Cloud App Security, debe realizar tres pasos:

1. [Compruebe los requisitos previos de licencia y administrador](#licensing-and-administrator-role-prerequisites).
1. [Regístrate para la prueba de gobernanza de aplicaciones](#sign-up-for-free-trial-of-app-governance).
1. [Agregar integración de MCAS](#add-integration-with-mcas).


## <a name="sign-up-for-free-trial-of-app-governance"></a>Regístrese para obtener una evaluación gratuita de gobernanza de aplicaciones

Para los clientes existentes de Microsoft 365:

1. Vaya a la página de registro[para obtener la evaluación gratuita](https://admin.microsoft.com/Commerce/Trial.aspx?OfferId=20be85b6-b196-402c-82b4-36b4e72862dc).
1. Complete los pasos para agregar gobernanza de aplicaciones. El registro es sencillo, tal como se muestra en el siguiente gráfico.

<!--
:::image type="content" source="../media/manage-app-protection-governance/sign-up-page.png" alt-text="Simple steps to add app governance to your account.":::
-->

Si aún no es cliente de Microsoft 365, puede registrarse para obtener una prueba gratuita:

1. En la parte superior de esta página, seleccione el botón  **Cuenta gratuita** .
1. En  **Probar Microsoft 365 para empresas** seleccione **Probar 1 mes gratis**.
1. Complete los pasos para el registro.

## <a name="add-integration-with-mcas"></a>Incorporación de la integración con MCAS

Requisitos previos:

- Office 365 está conectado en Cloud App Security
- Las aplicaciones de Microsoft Office 365 Azure AD están habilitadas

Para habilitar la sincronización de gobernanza de aplicaciones con Cloud App Security siga estos pasos:

1. Vaya al portal de Microsoft Cloud App Security: [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)
1. Seleccione el icono de engranaje (esquina superior derecha) y seleccione **Configuración**.
1. En **Protección contra amenazas**, seleccione **Gobernanza de aplicaciones**.
1. Seleccione **Habilitar la integración de Gobernanza de aplicaciones** y, a continuación, seleccione **Guardar**.

Para comprobar que la integración con MCAS está activa, busque las directivas de gobernanza de aplicaciones que se enumeran a continuación que aparecen en MCAS. Las nuevas directivas pueden tardar unos minutos en aparecer una vez habilitada la integración.

- Reputación de la aplicación de OAuth Microsoft 365
- Microsoft 365 detección de suplantación de identidad (phishing) de OAuth
- Microsoft 365 gobernanza de aplicaciones de OAuth

## <a name="licensing-and-administrator-role-prerequisites"></a>Requisitos previos de rol de administrador y licencias

1. Compruebe que su cuenta tenga el [nivel de licencias adecuado](#licensing-for-app-governance). La gobernanza de aplicaciones es un complemento para Microsoft Cloud App Security (MCAS) y, por tanto, MCAS debe estar presente en su cuenta como un producto independiente o como parte de los distintos paquetes de licencia.
1. Debe tener uno de los [roles de administrador](#administrator-roles) que se enumeran a continuación para acceder a las páginas de gobernanza de la aplicación en el portal.
1. La dirección de facturación de su organización debe estar dentro de una de las [áreas admitidas de Norteamérica, Europa o África](app-governance-countries.md) para activar la prueba gratuita.

### <a name="licensing-for-app-governance"></a>Licencias para la gobernanza de aplicaciones

Antes de empezar a trabajar con la gobernanza de aplicaciones, debería confirmar [Centro de administración de Microsoft 365: suscripciones](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/subscriptions) y los complementos. Para obtener acceso y usar la gobernanza de aplicaciones, su organización debe tener una de las siguientes suscripciones:

- Microsoft Cloud App Security
- Microsoft 365 (E5/A5)
- Cumplimiento de Microsoft 365 E5/A5 
- Gobernanza e Information Protection de Microsoft 365 E5/A5
- Seguridad de Microsoft 365 E5/A5
- Complemento de Cumplimiento de Microsoft 365 F5
- Complemento de Cumplimiento y de Seguridad de Microsoft 365 F5


### <a name="administrator-roles"></a>Roles de administrador

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

Estas son las funcionalidades de cada rol.

| Rol | Leer del panel | Leer todas las aplicaciones |Leer directivas | Crear, actualizar o eliminar directivas | Leer alertas | Actualizar alertas | Leer la configuración | Actualizar configuración | Leer corrección | Actualizar corrección |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| Administrador de la aplicación | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Administrador de aplicaciones en la nube | ![Marca de verificación](..\media\checkmark.png) | | | | | | | | | |
| Administrador de la empresa | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Administrador de cumplimiento | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Administrador de datos de cumplimiento | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Lector de cumplimiento | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | | |
| Lector global  | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | | |
| Administrador de seguridad | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Operador de seguridad | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Lector de seguridad  | ![Marca de verificación.](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | |
|||||||||| | |

Para obtener información adicional acerca de cada rol, consulte[permisos de rol de administrador](/azure/active-directory/roles/permissions-reference).

## <a name="canceling-your-trial"></a>Para cancelar la versión de prueba

Si no ha participado en la versión preliminar privada y desea cancelar la versión de prueba de gobernanza de aplicaciones, puede comunicarse con el contacto de CXE o seguir estos pasos:

1. En el Centro de administración de Microsoft 365, vaya a **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">**Sus productos**</a>.
1. Vaya a la prueba de gobernanza de aplicaciones, haga clic en los tres puntos y seleccione **Cancelar suscripción**.
1. En el panel flotante resultante, proporcione un motivo para la cancelación, cualquier comentario adicional y seleccione **Cancelar suscripción**.
1. Seleccione **Cancelar suscripción** en la pantalla emergente. La versión de prueba se ha cancelado. Perderá el acceso a la gobernanza de aplicaciones y se eliminarán los datos asociados (los datos de registro que se usan para crear la información y detecciones de la gobernanza de aplicaciones; ni los correos electrónico ni otros archivos se verán afectados).

## <a name="known-issues-for-the-public-preview"></a>Problemas conocidos para esta versión preliminar pública.

El equipo de gobernanza de aplicaciones ha identificado los siguientes problemas conocidos de la versión preliminar: 

- Sincronización bidireccional entre Microsoft Defender y las alertas de gobernanza de aplicaciones. Ahora las alertas resueltas en Defender también tendrán que resolverse manualmente en la gobernanza de aplicaciones.
