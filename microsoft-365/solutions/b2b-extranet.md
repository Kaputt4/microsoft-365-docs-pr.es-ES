---
title: Para obtener más información, consulte Crear una extranet de B2B con invitados administrados.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Obtenga información sobre cómo crear un sitio de extranet B2B o un equipo con invitados administrados de una organización asociada.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613601"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Para obtener más información, consulte Crear una extranet de B2B con invitados administrados.

Puede usar [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) para crear una extranet B2B para colaborar con una organización asociada que use Azure Active Directory. Esto permite a los usuarios inscribirse por sí solos en el sitio o equipo de extranet y recibir acceso a través de un flujo de trabajo de aprobación.

Con este método de compartir recursos para la colaboración, la organización asociada puede ayudar a mantener y aprobar a los invitados al final, lo que reduce la carga de su departamento de TI y permite a los usuarios más familiarizados con el contrato de colaboración administrar el acceso de los usuarios.

Este artículo describe los pasos para crear un paquete de recursos (en este caso, un sitio o equipo) que puede compartir con una organización asociada a través de un modelo de registro de acceso de autoservicio. 

Antes de empezar, cree el sitio o equipo que desea compartir con la organización asociada y habilite el uso compartido de invitados. Vea [Colaborar con invitados en un sitio](collaborate-in-site.md) o Colaborar con [invitados de un equipo](collaborate-as-team.md) para obtener más información. También le recomendamos que revise Crear un entorno seguro de uso compartido de invitados para obtener información sobre las características de seguridad y cumplimiento que puede usar para ayudar [a](create-secure-guest-sharing-environment.md) mantener las directivas de gobierno al colaborar con invitados.

## <a name="license-requirements"></a>Requisitos de licencia

El uso de esta característica requiere una licencia de Azure AD Premium P2. 

Las nubes especializadas, como Azure Alemania y Azure China 21Vianet, no están disponibles actualmente para su uso.

## <a name="video-demonstration"></a>Vídeo de demostración

En este vídeo se muestran los procedimientos tratados en este artículo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Conectar la organización asociada

Para invitar a invitados de una organización asociada, debes agregar el dominio del partner como una organización conectada en Azure Active Directory.

Para agregar una organización conectada
1. En [Azure Active Directory,](https://aad.portal.azure.com)haga clic en **Gobierno de identidades.**
2. Haga clic **en Organizaciones conectadas.**
4. Haga **clic en Agregar organización conectada.**
5. Escriba un nombre y una descripción para la organización y, a continuación, haga clic en **Siguiente: Directorio + dominio.**
6. Haga **clic en Agregar directorio + dominio.**
7. Escriba el dominio de la organización que desea conectar y, a continuación, haga clic en **Agregar**.
8. Haga **clic en Conectar** y, a continuación, haga clic en **Siguiente: Patrocinadores.**
9. Agregue personas de su organización o de la organización a las que se conecte a las personas a las que desee aprobar el acceso de los invitados.
10. Haga **clic en Siguiente: Revisar + Crear.**
11. Revise la configuración que ha elegido y, a continuación, haga clic en **Crear**.

    ![Captura de pantalla de la página de organizaciones conectadas en Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Elegir los recursos que se compartirán

El primer paso para seleccionar los recursos que se compartirán con una organización asociada es crear un catálogo que los contenga.

Para crear un catálogo
1. En [Azure Active Directory,](https://aad.portal.azure.com)haga clic en **Gobierno de identidades.**
2. Haga **clic en Catálogos**.
3. Haga **clic en Nuevo catálogo.**
4. Escriba un nombre y una descripción para el catálogo y asegúrese de que **Enabled** y **Enabled para usuarios** externos estén establecidos en **Sí.**
5. Haga clic en **Crear**.

   ![Captura de pantalla de la página catálogos en Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

Una vez creado el catálogo, agregue el sitio o el equipo de SharePoint que desea compartir con la organización asociada.

Para agregar recursos a un catálogo
1. En Azure AD Identity Governance, haga clic en **Catálogos** y, a continuación, haga clic en el catálogo donde desea agregar recursos.
2. Haga **clic en Recursos** y, a **continuación, haga clic en Agregar recursos.**
3. Seleccione los equipos o sitios de SharePoint que desea incluir en la extranet y, a continuación, haga clic en **Agregar**.

   ![Captura de pantalla de la página de recursos del catálogo en Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

Una vez que hayas definido los recursos que quieres compartir, el siguiente paso es crear un paquete de acceso, que define el tipo de acceso que se concede a los usuarios asociados y el proceso de aprobación para los nuevos usuarios asociados que solicitan acceso.

Para crear un paquete de acceso
1. En Azure AD Identity Governance, haga clic en **Catálogos** y, a continuación, haga clic en el catálogo donde desea crear un paquete de acceso.
2. Haga clic **en Paquetes de Access** y, a continuación, haga clic en Nuevo paquete de **acceso.**
3. Escriba un nombre y una descripción para el paquete de acceso y, a continuación, haga clic en **Siguiente: Roles de recursos.**
4. Elija los recursos del catálogo que desea usar para la extranet.
5. Para cada recurso, en la **columna Rol,** elija el rol de usuario que desea conceder a los invitados que usan la extranet.
6. Haga **clic en Siguiente: Solicitudes.**
7. En **Usuarios que pueden solicitar acceso,** elija Para usuarios que no están en el **directorio.**
8. Asegúrese de que **la opción Organizaciones conectadas** específicas esté seleccionada y, a continuación, haga clic **en Agregar directorios.**
9. Elija la organización conectada que agredía anteriormente y, a continuación, haga clic en **Seleccionar**
10. En **Aprobación,** elija **Sí** para **Requerir aprobación.**
11. En **Primer aprobador,** elija uno de los patrocinadores que agregó anteriormente o elija un usuario específico.
12. Haz **clic en Agregar reserva** y selecciona un aprobador de reserva.
13. En **Habilitar**, elija **Sí**.
14. Haga **clic en Siguiente: Ciclo de vida.**
15. Elija la configuración de expiración y acceso a la revisión que desea usar y, a continuación, haga clic en **Siguiente: Revisar + Crear.**
16. Revise la configuración y, a continuación, haga clic **en Crear**.

    ![Captura de pantalla de la pantalla de paquetes de acceso en Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Si te asocias con una organización grande, es posible que quieras ocultar el paquete de acceso. Si el paquete está oculto, los usuarios de la organización asociada no verán el paquete en su portal *de Mi acceso.* En su lugar, se les debe enviar un vínculo directo para registrarse en el paquete. Ocultar el paquete de acceso puede reducir el número de solicitudes de acceso inadecuadas y también puede ayudar a mantener los paquetes de acceso disponibles organizados en el portal de la organización asociada.

Para establecer un paquete de acceso en oculto
1. En Azure AD Identity Governance, haga clic en **Paquetes de Access** y, a continuación, haga clic en el paquete de acceso.
2. En la página **Información** general, haga clic **en Editar**.
3. En **Propiedades,** elija **Sí** para **Oculto** y, a continuación, haga clic en **Guardar**.

   ![Captura de pantalla de una pantalla de propiedades del paquete de acceso de edición](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Invitar a usuarios asociados

Si estableces el paquete de acceso en oculto, debes enviar un vínculo directo a la organización asociada para que puedan solicitar acceso a tu sitio o equipo.

Para buscar el vínculo del portal de acceso
1. En Azure AD Identity Governance, haga clic en **Paquetes de Access** y, a continuación, haga clic en el paquete de acceso.
2. En la página **Información** general, haga clic **en el** vínculo Copiar al Portapapeles del vínculo Portal de **Mi acceso.**

   ![Captura de pantalla de las propiedades del paquete de acceso con el vínculo del portal de acceso](../media/identity-governance-access-portal-link.png)

Una vez que haya copiado el vínculo, puede compartirlo con su contacto en la organización asociada y puede enviarlo a los usuarios de su equipo de colaboración.

## <a name="see-also"></a>Vea también

[Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)
