---
title: Configuración de las opciones de versión estándar o de destino
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Obtenga información sobre cómo configurar la opción de versión para nuevas actualizaciones de productos y características en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 67c6fe3f08549424c725589a50c647a876c151af
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "65022457"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Configuración de las opciones de versión estándar o de destino

> [!IMPORTANT]
> Las actualizaciones Microsoft 365 descritas en este artículo se aplican a Microsoft 365, SharePoint Online y Exchange Online. Estas opciones de versión tienen como destino las mejores formas de liberar cambios en Microsoft 365, pero no se pueden garantizar en todo momento ni para todas las actualizaciones. No se aplican a Aplicaciones Microsoft 365, Skype Empresarial, Microsoft Teams y servicios relacionados. Para obtener información sobre las opciones de versión de Aplicaciones Microsoft 365, consulte [Información general sobre los canales de actualización para Aplicaciones Microsoft 365](/deployoffice/overview-update-channels).

Con Microsoft 365, recibirá nuevas actualizaciones de productos y características a medida que estén disponibles en lugar de realizar actualizaciones costosas cada pocos años. Puede administrar cómo su organización recibe estas actualizaciones. Por ejemplo, puede registrarse para obtener una versión anticipado y que su organización reciba actualizaciones en primer lugar. Puede elegir que solo determinados individuos reciban las actualizaciones. También puede elegir permanecer en el calendario de publicaciones predeterminado y recibir las actualizaciones más tarde. En este artículo se explican las distintas opciones de versión y cómo puede usarlas para su organización.

## <a name="how-it-works---release-validation"></a>Cómo funciona: validación de versiones

Cualquier nueva versión se prueba y valida primero por el equipo de características y, después, por todo el equipo de características de Microsoft 365, seguido de todo Microsoft. Después de la validación y las pruebas internas, el siguiente paso es una **Versión dirigida** (anteriormente conocida como First Release) para los clientes que hayan decidido participar. En cada anillo de versión, Microsoft recopila comentarios y valida posteriormente la calidad mediante la supervisión de métricas de uso claves. Esta serie de validaciones progresivas se realiza de forma local para asegurar que la versión publicada mundialmente es tan sólida como sea posible. Las versiones se representan en la siguiente ilustración. 
  
![Anillos de validación de versión para Microsoft 365.](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
En el caso de actualizaciones significativas, la hoja de [ruta de Microsoft 365](https://products.office.com/business/office-365-roadmap) notifica inicialmente a los clientes. A medida que una actualización se acerca a la implementación, se comunica a través del [centro de mensajes de Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> Necesita una cuenta de Microsoft 365 o Azure AD para acceder al Centro de mensajes a través del [centro de administración](/office365/admin/admin-overview/about-the-admin-center). Microsoft 365 los usuarios del plan principal no tienen un centro de administración.

## <a name="standard-release"></a>Versión estándar

Esta es la opción predeterminada en la que usted y los usuarios reciben las actualizaciones más recientes cuando se publican ampliamente para todos los clientes.
  
Una buena práctica consiste en dejar a la mayoría de los usuarios en **la versión Estándar** y a los profesionales de TI y a los usuarios avanzados en **la versión dirigida** para evaluar nuevas características y preparar equipos para dar soporte a usuarios empresariales y ejecutivos. 
  
> [!NOTE]
> Si cambia de la versión dirigida a la versión estándar, es posible que los usuarios pierdan el acceso a características que aún no han llegado a la versión estándar. 
  
## <a name="targeted-release"></a>Versión dirigida

Con esta opción, usted y sus usuarios pueden ser los primeros en ver las últimas actualizaciones y ayudar a dar forma al producto al proporcionar comentarios anticipados. Puede elegir que los individuos o toda la organización reciban actualizaciones anticipadas.
  
> [!IMPORTANT]
> - Las actualizaciones complejas o de gran tamaño pueden tardar más que otras para que los usuarios no se vean afectados negativamente. No hay ninguna garantía de la cronología exacta de un lanzamiento.
> - La versión dirigida no está disponible actualmente para los clientes con el plan de Office 365 GCC o el plan Office 365 GCC High y DoD.
  
### <a name="targeted-release-for-entire-organization"></a>Versión dirigida para toda la organización

Si [configura la opción de versión en el Centro de administración](#set-up-the-release-option-in-the-admin-center) para esta opción, todos los usuarios obtendrán la experiencia de versión dirigida. Para organizaciones con más de 300 usuarios, le recomendamos usar una suscripción de prueba para esta opción. Para obtener información acerca de las suscripciones de prueba, póngase en contacto con Microsoft. 
  
### <a name="targeted-release-for-selected-users"></a>Versión dirigida para usuarios seleccionados

Si [configura la opción de versión en el Centro de administración](#set-up-the-release-option-in-the-admin-center) para esta opción, puede definir usuarios específicos, normalmente usuarios avanzados, para recibir acceso anticipado a las características y la funcionalidad.

> [!IMPORTANT]
> Algunas características solo se implementarán por organización. Esto significa que toda la organización recibirá acceso a la característica al mismo tiempo. En el caso de características como esta, no es posible que los usuarios seleccionados en el programa de versión de destino obtengan la característica antes de tiempo. Esto significa que su organización no podrá recibir estas características al principio si ha configurado usuarios seleccionados en la versión de destino. Para asegurarse de que ve todas las características en la versión de destino, deberá configurar la versión de destino para toda la organización o configurar una organización de prueba.
  
## <a name="benefits-of-targeted-release"></a>Ventajas de la Versión dirigida

La versión dirigida permite a los administradores, administradores de cambios o cualquier otra persona responsable de Microsoft 365 actualizaciones prepararse para los próximos cambios, permitiéndoles:
  
- Prueba y validación de nuevas actualizaciones antes de publicarlas para todos los usuarios de la organización.
    
- Preparación de documentación y notificaciones para los usuarios antes de publicar las actualizaciones.
    
- Preparación de asistencia interna para los próximos cambios.
    
- Revisión de seguridad y cumplimiento.
    
- Uso de controles de características, donde se pueda, para controlar la publicación de características para los usuarios finales.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Configuración de la opción de versión en el Centro de administración

Para cambiar la forma en que la organización recibe actualizaciones Microsoft 365, siga estos pasos. Debe ser administrador global en Microsoft 365 para participar.
  
> [!IMPORTANT]
> Los cambios siguientes pueden tardar hasta 24 horas en surtir efecto en Microsoft 365. Si opta por una opción distinta a la versión dirigida después de activarlo, puede que los usuarios pierdan el acceso a características que todavía no han alcanzado la versión programada. 
  
1. En el centro de administración, vaya a la **configuración de Configuración** >  **Org** y, en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">pestaña **Perfil**</a> de la organización, elija **Preferencias de versión**.

5. Para deshabilitar la versión de destino, seleccione **Versión estándar** y, a continuación, seleccione **Guardar cambios**. 
    
6. Para habilitar la versión de destino para todos los usuarios de la organización, seleccione **Versión dirigida para todos los usuarios** y, a continuación, seleccione **Guardar cambios**. 
    
7. Para habilitar la versión de destino para algunas personas de la organización, seleccione **Versión dirigida para los usuarios seleccionados** y, a continuación, seleccione **Guardar cambios**. 
    
8. Elija **Seleccionar usuarios** para agregar usuarios de uno en uno o **Upload usuarios** para agregarlos de forma masiva.
    
9. Cuando haya terminado de agregar usuarios, seleccione **Guardar cambios**.
  
## <a name="next-steps"></a>Siguientes pasos

Descubra cómo [administrar mensajes](/office365/admin/manage/message-center) en [el centro de mensajes de Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obtener notificaciones sobre las próximas actualizaciones y versiones de Microsoft 365.

## <a name="related-content"></a>Contenido relacionado

[Unirse al programa Office Insider](https://insider.office.com/join/windows) (artículo)
