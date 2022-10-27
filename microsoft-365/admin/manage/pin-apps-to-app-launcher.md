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
- Tier3
- scotvorg
- Adm_O365
- M365-subscription-management
- Adm_TOC
ms.service: microsoft-365-business
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
description: Como administrador global, puede anclar hasta tres aplicaciones al iniciador de aplicaciones de los usuarios.
ms.openlocfilehash: d3f6874fc0aa3a0731fd426f4d9a110b2b6c4632
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731775"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Anclar aplicaciones al iniciador de aplicaciones de los usuarios

Puede usar controles en el portal de Azure Active Directory para anclar hasta tres aplicaciones a Office.com y el iniciador de aplicaciones para todos los usuarios de la organización. También puede organizar grupos de aplicaciones. El usuario puede desanclar posteriormente cualquier aplicación que agregue en cualquier momento. Para anclar una aplicación para los usuarios, debe ser administrador de aplicaciones en la nube, administrador de aplicaciones en Azure Active Directory o Administrador global en Microsoft 365. Para obtener más información sobre los roles de administrador, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference) y [roles de administrador en Microsoft 365](../add-users/about-admin-roles.md). 

Para obtener más información sobre el iniciador de aplicaciones y Office.com, consulta [el artículo de blog sobre el iniciador](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) de aplicaciones [y las actualizaciones de office.com y el iniciador de aplicaciones Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503).

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Uso del portal de Azure Active Directory para anclar aplicaciones

> [!NOTE]
> Las aplicaciones de Microsoft 365 se excluyen de esta lista, ya que ya se muestran en el iniciador de aplicaciones.

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.
2. En el panel de navegación izquierdo, elija **Mostrar todo** y, en **Administración centros**, elija **Azure Active Directory**.
3. En **Azure Active Directory**, elija **Aplicaciones empresariales** > **Configuración de usuario**.
4. En la sección **Configuración de Office 365**, elija **Agregar aplicación**.
5. Elija las aplicaciones que desea anclar al iniciador de aplicaciones de los usuarios y, a continuación, elija **Agregar**.

:::image type="content" source="../../media/add-apps.png" alt-text="Configuración de Microsoft 365 para anclar aplicaciones.":::

### <a name="pin-a-custom-app"></a>Anclar una aplicación personalizada

> [!NOTE]
> La interfaz de usuario indicará si necesita comprar licencias de Azure AD adicionales para usar esta característica. Para obtener más información, consulte [Precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

1. En **Azure Active Directory**, elija **Aplicaciones empresariales** > **Nueva aplicación** en la parte superior de la página **Todas las aplicaciones** .
2. En la página **Agregar una aplicación** , elija **Aplicación que no sea de la galería** o **Crear su propia aplicación** si se encuentra en la versión preliminar de Azure Active Directory. 
3. Escriba un nombre para la aplicación y, a continuación, asigne un usuario en la pestaña **Usuarios y grupos** .
4. Use la pestaña **Propiedades** para cargar un icono para la aplicación.
5. Para asignar una dirección URL a la aplicación, en la pestaña **Inicio de sesión único** , elija **Vinculado** y escriba una dirección URL.
6. Seleccione **Guardar**.

## <a name="create-application-collections"></a>Creación de colecciones de aplicaciones

También puede crear colecciones de aplicaciones para los usuarios de su organización. Para obtener instrucciones, consulte [Creación de colecciones en el portal de Aplicaciones en el Azure Portal](/azure/active-directory/manage-apps/access-panel-collections).