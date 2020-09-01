---
title: Anclar aplicaciones al iniciador de aplicaciones de los usuarios
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Como administrador global, puede anclar hasta tres aplicaciones al iniciador de aplicaciones de los usuarios.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310880"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Anclar aplicaciones al iniciador de aplicaciones de los usuarios

Puede usar controles en el portal de Azure Active Directory para anclar hasta tres aplicaciones a Office.com y el iniciador de aplicaciones para todos los usuarios de la organización. También puede organizar grupos de aplicaciones. Más adelante, el usuario podrá desanclar cualquier aplicación que agregue en cualquier momento. Para anclar una aplicación a los usuarios, debe ser un administrador de la aplicación de nube o un administrador de aplicaciones en Azure Active Directory, o un administrador global de Office 365. Para obtener más información acerca de los roles de administrador, vea [roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) y [roles de administrador en Microsoft 365](../add-users/about-admin-roles.md). 

Para obtener más información sobre el iniciador de aplicaciones y Office.com, vea [reunirse con el iniciador de aplicaciones](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) y [actualizaciones a Office.com y el artículo del blog del iniciador de aplicaciones de Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) .

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Usar el portal de Azure Active Directory para anclar aplicaciones

1. Vaya al centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. En el panel de navegación izquierdo, elija **Mostrar todo**y, en **centros de administración**, elija **Azure Active Directory**.
3. En **Azure Active Directory**, elija Configuración de usuario de **aplicaciones empresariales**  >  **User settings**.
4. En la sección **configuración de Office 365** , elija **Agregar aplicación**.
5. Elija las aplicaciones que quiera anclar en el iniciador de aplicaciones de los usuarios y luego elija **Agregar**.

:::image type="content" source="../../media/add-apps.png" alt-text="Configuración de Microsoft 365 para anclar aplicaciones.":::

### <a name="pin-a-custom-app"></a>Anclar una aplicación personalizada

> [!NOTE]
> La interfaz de usuario le indicará si necesita comprar licencias de Azure AD adicionales para usar esta característica. Para obtener más información, vea [precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

1. En **Azure Active Directory**, elija **Enterprise applications**  >  **nueva aplicación** de aplicaciones empresariales en la parte superior de la página **todas las aplicaciones** .
2. En la página **Agregar una aplicación** , elija **aplicación que no sea de Galería** o **cree su propia aplicación** si se encuentran en la versión preliminar de Azure Active Directory. 
3. Escriba un nombre para la aplicación y, después, asignar usuario en la pestaña **usuarios y grupos** .
4. Use la pestaña **propiedades** para cargar un icono para la aplicación.
5. Para asignar una dirección URL a la aplicación, en la pestaña **Inicio de sesión único** , elija **vinculado** y, a continuación, escriba una dirección URL.
6. Seleccione **Guardar**.

## <a name="create-application-collections"></a>Crear colecciones de aplicaciones

También puede crear colecciones de aplicaciones para los usuarios de la organización. Para obtener instrucciones, vea [crear colecciones en el portal mis aplicaciones en el portal de Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).