---
title: Configurar las opciones de versión estándar o dirigida
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Obtenga información sobre cómo configurar la opción de lanzamiento para actualizaciones de nuevos productos y características en el centro de administración Microsoft 365 de administración.
ms.openlocfilehash: 5060e2dc99355d89928ec91c96b7d25e2016c7c4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593950"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Configurar las opciones de versión estándar o dirigida

> [!IMPORTANT]
> Las Microsoft 365 que se describen en este artículo se aplican a Microsoft 365, SharePoint Online y Exchange Online. Estas opciones de versión son formas dirigidas y de mayor esfuerzo para liberar cambios en Microsoft 365 pero no se pueden garantizar en todo momento ni para todas las actualizaciones. No se aplican a Aplicaciones Microsoft 365, Skype Empresarial, Microsoft Teams y servicios relacionados. Para obtener información acerca de las opciones de Aplicaciones Microsoft 365, vea [Overview of update channels for Aplicaciones Microsoft 365](/deployoffice/overview-update-channels).

Con Microsoft 365, recibirá nuevas actualizaciones de productos y características a medida que estén disponibles en lugar de realizar actualizaciones costosas cada pocos años. Puede administrar cómo su organización recibe estas actualizaciones. Por ejemplo, puede registrarse para obtener una versión anticipado y que su organización reciba actualizaciones en primer lugar. Puede elegir que solo determinados individuos reciban las actualizaciones. También puede elegir permanecer en el calendario de publicaciones predeterminado y recibir las actualizaciones más tarde. En este artículo se explican las distintas opciones de versión y cómo puede usarlas para su organización.

## <a name="how-it-works---release-validation"></a>Cómo funciona: validación de versiones

Cualquier nueva versión primero se prueba y valida por el equipo de características, después por todo el Microsoft 365 de características, seguido de todo Microsoft. Después de la validación y las pruebas internas, el siguiente paso es una **Versión dirigida** (anteriormente conocida como First Release) para los clientes que hayan decidido participar. En cada anillo de versión, Microsoft recopila comentarios y valida posteriormente la calidad mediante la supervisión de métricas de uso claves. Esta serie de validaciones progresivas se realiza de forma local para asegurar que la versión publicada mundialmente es tan sólida como sea posible. Las versiones se representan en la siguiente ilustración. 
  
![Liberar anillos de validación para Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Para actualizaciones significativas, los clientes son notificados inicialmente por [el Microsoft 365 guía básica](https://products.office.com/business/office-365-roadmap). A medida que una actualización está más cerca de implementarse, se comunica a través Microsoft 365 [centro de mensajes](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> Necesita una cuenta Microsoft 365 o azure AD para tener acceso a su Centro de mensajes a través del [Centro de administración.](/office365/admin/admin-overview/about-the-admin-center) Microsoft 365 usuarios del plan principal no tienen un centro de administración.


## <a name="standard-release"></a>Versión estándar

Esta es la opción predeterminada en la que usted y sus usuarios reciben las actualizaciones más recientes cuando se lanzan ampliamente a todos los clientes.
  
Una buena práctica es dejar a  la mayoría de los usuarios  en la versión estándar y a los profesionales de IT y usuarios avanzados en la versión dirigida para evaluar nuevas características y preparar equipos para admitir a los usuarios y ejecutivos empresariales. 
  
> [!NOTE]
> Si cambia de la versión dirigida a la versión estándar, es posible que los usuarios pierdan el acceso a características que aún no han llegado a la versión estándar. 
  
## <a name="targeted-release"></a>Versión dirigida

Con esta opción, usted y sus usuarios pueden ser los primeros en ver las últimas actualizaciones y ayudar a dar forma al producto al proporcionar comentarios anticipados. Puede elegir que los individuos o toda la organización reciban actualizaciones anticipadas.
  
> [!IMPORTANT]
> Las actualizaciones complejas o de gran tamaño pueden tardar más que otras para que los usuarios no se vean afectados negativamente. No hay ninguna garantía de la cronología exacta de un lanzamiento. 
  
### <a name="targeted-release-for-entire-organization"></a>Versión dirigida para toda la organización

Si configura [la opción de versión en](#set-up-the-release-option-in-the-admin-center) el Centro de administración para esta opción, todos los usuarios tendrán la experiencia de versión dirigida. Para organizaciones con más de 300 usuarios, le recomendamos usar una suscripción de prueba para esta opción. Para obtener información acerca de las suscripciones de prueba, póngase en contacto con Microsoft. 
  
### <a name="targeted-release-for-selected-users"></a>Versión dirigida para usuarios seleccionados

Si configura [la opción de](#set-up-the-release-option-in-the-admin-center) versión en el Centro de administración para esta opción, puede definir usuarios específicos, normalmente usuarios avanzados, para recibir acceso anticipado a características y funcionalidades. 
  
## <a name="benefits-of-targeted-release"></a>Ventajas de la Versión dirigida

La versión dirigida permite a los administradores, los administradores de cambios o cualquier otra persona responsable de Microsoft 365 actualizaciones prepararse para los próximos cambios al permitirles:
  
- Prueba y validación de nuevas actualizaciones antes de publicarlas para todos los usuarios de la organización.
    
- Preparación de documentación y notificaciones para los usuarios antes de publicar las actualizaciones.
    
- Preparación de asistencia interna para los próximos cambios.
    
- Revisión de seguridad y cumplimiento.
    
- Uso de controles de características, donde se pueda, para controlar la publicación de características para los usuarios finales.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Configurar la opción de versión en el Centro de administración

Puede cambiar el modo en que su organización recibe Microsoft 365 actualizaciones siguiendo estos pasos. Debes ser un administrador global en Microsoft 365 participar.
  
> [!IMPORTANT]
> Los cambios siguientes pueden tardar hasta 24 horas en tener efecto en Microsoft 365. Si opta por una opción distinta a la versión dirigida después de activarlo, puede que los usuarios pierdan el acceso a características que todavía no han alcanzado la versión programada. 
  
1. En el Centro de administración, vaya a la configuración Configuración organización y, en la pestaña Perfil de la  >  organización, elija **Preferencias de versión.** 

5. Para deshabilitar la versión dirigida, seleccione **Versión estándar** y, a continuación, seleccione **Guardar cambios**. 
    
6. Para habilitar la versión dirigida para todos los usuarios de la organización, seleccione **Versión dirigida** para todos los usuarios y, a continuación, seleccione **Guardar cambios**. 
    
7. Para habilitar la versión dirigida para algunas personas de la organización, seleccione **Versión dirigida** para usuarios seleccionados y, a continuación, seleccione **Guardar cambios**. 
    
8. Elija **Seleccionar usuarios** para agregar usuarios de uno en uno, o Upload **usuarios** para agregarlos en masa.
    
9. Cuando haya terminado de agregar usuarios, seleccione **Guardar cambios**.
  
## <a name="next-steps"></a>Pasos siguientes

Descubra cómo administrar [mensajes en](/office365/admin/manage/message-center) su centro de [Microsoft 365 mensajes](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obtener notificaciones acerca de las próximas Microsoft 365 actualizaciones y versiones.

## <a name="related-content"></a>Contenido relacionado

[Unirse al Office Insider Program](https://insider.office.com/join/windows) (artículo)
