---
title: Anclar aplicaciones al iniciador de aplicaciones de los usuarios
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Como administrador global, puedes anclar hasta tres aplicaciones al iniciador de aplicaciones de los usuarios.
ms.openlocfilehash: 786368f1236c7a86a6fbd0dd863ad0296cb65fac
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579271"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Anclar aplicaciones al iniciador de aplicaciones de los usuarios

Puede usar controles en el portal de Azure Active Directory para anclar hasta tres aplicaciones para Office.com y el iniciador de aplicaciones para todos los usuarios de la organización. También puede organizar grupos de aplicaciones. Cualquier aplicación que agregues más adelante puede desanclarla el usuario en cualquier momento. Para anclar una aplicación para los usuarios, debe ser administrador de aplicaciones en la nube, administrador de aplicaciones en Azure Active Directory o administrador global en Office 365. Para obtener más información acerca de los roles de administrador, vea [Roles de administrador](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) en Azure Active Directory y Roles de administrador en Microsoft [365](../add-users/about-admin-roles.md). 

Para obtener más información sobre el iniciador [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) de aplicaciones y Office.com, vea el artículo sobre el iniciador de aplicaciones y las actualizaciones de office.com y el artículo del blog del iniciador de aplicaciones de [Office 365.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Usar el portal de Azure Active Directory para anclar aplicaciones

1. Vaya al Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. En el panel de navegación izquierdo, elija **Mostrar todo** y, en Centros **de administración,** elija **Azure Active Directory**.
3. En **Azure Active Directory,** elija **Aplicaciones empresariales**  >  **Configuración de usuario**.
4. En la **sección Configuración de Office 365,** elija Agregar **aplicación**.
5. Elija las aplicaciones que desea anclar al iniciador de aplicaciones de los usuarios y, a continuación, **elija Agregar**.

:::image type="content" source="../../media/add-apps.png" alt-text="Configuración de Microsoft 365 para anclar aplicaciones.":::

### <a name="pin-a-custom-app"></a>Anclar una aplicación personalizada

> [!NOTE]
> La interfaz de usuario indicará si necesita comprar licencias adicionales de Azure AD para usar esta característica. Para obtener más información, [vea Precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

1. En **Azure Active Directory,** elija **Aplicaciones empresariales**  >  **Nueva aplicación** en la parte superior de la página Todas **las** aplicaciones.
2. En la **página Agregar una aplicación,**  elija Aplicación que no sea **de galería** o Cree su propia aplicación si está en la versión preliminar de Azure Active Directory. 
3. Escriba un nombre para la aplicación y, a continuación, asigne usuario en la **pestaña Usuarios y** grupos.
4. Usa la **pestaña** Propiedades para cargar un icono para la aplicación.
5. Para asignar una dirección URL a la aplicación, en la pestaña Inicio de sesión **único,** elija **Vinculado** y, a continuación, escriba una dirección URL.
6. Seleccione **Guardar**.

## <a name="create-application-collections"></a>Crear colecciones de aplicaciones

También puede crear colecciones de aplicaciones para los usuarios de su organización. Para obtener instrucciones, consulte [Create collections on the My Apps portal in the Azure Portal](/azure/active-directory/manage-apps/access-panel-collections).