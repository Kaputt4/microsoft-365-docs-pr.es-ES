---
title: Implementar sitios de SharePoint Online con tres niveles de protección
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Resumen: Cree y configure sitios de grupo de SharePoint Online con distintos niveles de protección de la información.'
ms.openlocfilehash: 1f67dd1956059162902aefdb194e5e514d063778
ms.sourcegitcommit: a53ec6ab7bf59983780ea7187cd5d56b8b1f4b33
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "41855259"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>Implementar sitios de SharePoint Online con tres niveles de protección

Siga los pasos de este artículo para diseñar e implementar sitios de grupo de base de referencia, confidenciales y extremadamente confidenciales de SharePoint Online. Para más información sobre estos tres niveles de protección, vea [Proteger sitios y archivos de SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).
  
## <a name="baseline-sharepoint-online-team-sites"></a>Sitios de grupo de base de referencia de SharePoint Online

La protección de base de referencia incluye sitios de grupo públicos y privados. Todo el personal de la organización puede acceder a los sitios de grupo públicos. Solo los miembros del grupo de Office 365 asociado al sitio de grupo pueden detectar sitios privados y acceder a ellos. Ambos tipos de sitios de grupo permiten a los miembros compartir el sitio con otros usuarios.
  
### <a name="public"></a>Público

Para crear un sitio de grupo de SharePoint Online de línea base con acceso y permisos públicos, siga [estas instrucciones](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Esta es la configuración resultante.
  
![Protección de nivel de línea base de un sitio de grupo de SharePoint Online público.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>Privado

Para crear un sitio de grupo de SharePoint Online de línea base con acceso y permisos privados, siga [estas instrucciones](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).
  
Esta es la configuración resultante.
  
![Protección de nivel de línea base de un sitio de grupo de SharePoint Online privado.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>Sitios de grupo confidenciales de SharePoint Online

Un sitio de grupo confidencial de SharePoint Online empieza como un sitio de grupo privado.
  
Primero, cree el sitio de grupo de SharePoint Online privado mediante [estas instrucciones](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Después, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos adicionales con estos pasos.

1.  En la barra de herramientas, haga clic en el sitio de grupo de SharePoint, en el icono de configuración y, luego, en **Permisos del sitio**.
2.  En el panel **Permisos del sitio**, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
3.  En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas, además del sitio** y, luego, haga clic en **Guardar**.

Los resultados de esta configuración de permisos son los siguientes:

- La capacidad de compartir con otros miembros está deshabilitada.
- La capacidad de los no miembros de solicitar acceso está deshabilitada.

Esta es la configuración resultante.
  
![Protección de nivel confidencial de un sitio de grupo aislado de SharePoint Online.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
Los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar de forma segura en los recursos del sitio.
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>Sitios de grupo de SharePoint Online extremadamente confidenciales

Un sitio de grupo de SharePoint Online extremadamente confidencial es un sitio de grupo privado con una configuración de permisos adicional.

Primero, cree el sitio de grupo de SharePoint Online privado mediante [estas instrucciones](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

Después, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos adicionales con estos pasos.

1.  En la barra de herramientas, haga clic en el sitio de grupo de SharePoint, en el icono de configuración y, luego, en **Permisos del sitio**.
2.  En el panel **Permisos del sitio**, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
3.  En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.
4. Desactive **Permitir solicitudes de acceso** y, después, haga clic en **Guardar**.

Los resultados de esta configuración de permisos son los siguientes:

- La capacidad de compartir con otros miembros está deshabilitada.
- La capacidad de los no miembros de solicitar acceso está deshabilitada.

Esta es la configuración resultante.
  
![Protección de nivel Extremadamente confidencial de un sitio de grupo aislado de SharePoint Online.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
Los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar de forma segura en los recursos del sitio.
  
## <a name="next-step"></a>Paso siguiente

[Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>Vea también

[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
