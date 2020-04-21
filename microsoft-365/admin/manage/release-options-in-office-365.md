---
title: Configurar las opciones estándar o de lanzamiento de destino
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Obtenga información sobre cómo configurar la opción de lanzamiento de actualizaciones de productos y características nuevas en el centro de administración de Microsoft 365.
ms.openlocfilehash: 11672e46acb3124c8fd840ab19ee683cfd6af94f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628117"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Configurar las opciones estándar o de lanzamiento de destino

Con Microsoft 365, recibirá nuevas actualizaciones de productos y características a medida que estén disponibles en lugar de realizar actualizaciones costosas cada pocos años. Puede administrar cómo su organización recibe estas actualizaciones. Por ejemplo, puede registrarse para obtener una versión anticipado y que su organización reciba actualizaciones en primer lugar. Puede elegir que solo determinados individuos reciban las actualizaciones. También puede elegir permanecer en el calendario de publicaciones predeterminado y recibir las actualizaciones más tarde. En este artículo se explican las diferentes opciones de versiones y cómo puede usarlas para su organización.
  
> [!IMPORTANT]
> Las actualizaciones de Microsoft 365 descritas en este artículo se aplican a Microsoft 365, SharePoint Online y Exchange Online. No se aplican a Skype Empresarial ni a los servicios relacionados. Estas opciones de versión están dirigidas a los mejores esfuerzos para publicar cambios en Microsoft 365, pero no se pueden garantizar en todo momento ni para todas las actualizaciones. 
  
## <a name="how-it-works---release-validation"></a>Cómo funciona: validación de versiones

Las nuevas versiones se prueban y validan por primera vez por el equipo de características y, a continuación, por todo el equipo de características de Microsoft 365, seguidos de todo Microsoft. Después de la validación y las pruebas internas, el siguiente paso es una **Versión dirigida** (anteriormente conocida como First Release) para los clientes que hayan decidido participar. En cada anillo de versión, Microsoft recopila comentarios y valida posteriormente la calidad mediante la supervisión de métricas de uso claves. Esta serie de validaciones progresivas se realiza de forma local para asegurar que la versión publicada mundialmente es tan sólida como sea posible. Las versiones se representan en la siguiente ilustración. 
  
![Liberar timbres de validación para Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Para las actualizaciones importantes, los clientes de Office se notifican inicialmente mediante el [plan de desarrollo de Microsoft 365](https://products.office.com/business/office-365-roadmap). A medida que se acerca la actualización, se comunica a través del centro de [mensajes de Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> Necesita una cuenta de Microsoft 365 o de Azure AD para obtener acceso al centro de mensajes a través del [centro de administración](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center). Los usuarios del plan de inicio de Microsoft 365 no tienen un centro de administración.


## <a name="standard-release"></a>Versión estándar

Esta es la opción predeterminada en la que usted y sus usuarios reciben las actualizaciones más recientes cuando se publican ampliamente para todos los clientes.
  
Un procedimiento recomendado es dejar la mayoría de los usuarios en **versiones estándar** y profesionales de ti y usuarios avanzados en el **lanzamiento de destino** para evaluar nuevas características y preparar a Microsoft Teams para que admitan usuarios y ejecutivos empresariales. 
  
> [!NOTE]
> Si cambia de la versión dirigida a la versión estándar, es posible que los usuarios pierdan el acceso a características que aún no han llegado a la versión estándar. 
  
## <a name="targeted-release"></a>Versión dirigida

Con esta opción, usted y sus usuarios pueden ser los primeros en ver las últimas actualizaciones y ayudar a dar forma al producto al proporcionar comentarios anticipados. Puede elegir que los individuos o toda la organización reciban actualizaciones anticipadas.
  
> [!IMPORTANT]
> Las actualizaciones complejas o de gran tamaño pueden tardar más que otras para que los usuarios no se vean afectados negativamente. No hay ninguna garantía de la cronología exacta de un lanzamiento. 
  
### <a name="targeted-release-for-entire-organization"></a>Versión dirigida para toda la organización

Si [configura la opción liberar en el centro de administración](#set-up-the-release-option-in-the-admin-center) de esta opción, todos los usuarios obtendrán la experiencia de la versión de destino. Para organizaciones con más de 300 usuarios, le recomendamos usar una suscripción de prueba para esta opción. Para obtener información acerca de las suscripciones de prueba, póngase en contacto con Microsoft. 
  
### <a name="targeted-release-for-selected-users"></a>Versión dirigida para usuarios seleccionados

Si [configura la opción liberar en el centro de administración](#set-up-the-release-option-in-the-admin-center) de esta opción, puede definir usuarios específicos, normalmente usuarios avanzados, para que obtengan acceso anticipado a características y funcionalidad. 
  
## <a name="benefits-of-targeted-release"></a>Ventajas de la Versión dirigida

La versión dirigida permite que los administradores, administradores de cambios o cualquier otra persona responsable de las actualizaciones de Microsoft 365 se prepare para preparar los próximos cambios al permitirles:
  
- Prueba y validación de nuevas actualizaciones antes de publicarlas para todos los usuarios de la organización.
    
- Preparación de documentación y notificaciones para los usuarios antes de publicar las actualizaciones.
    
- Preparación de asistencia interna para los próximos cambios.
    
- Revisión de seguridad y cumplimiento.
    
- Uso de controles de características, donde se pueda, para controlar la publicación de características para los usuarios finales.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Configurar la opción de lanzamiento en el centro de administración

Puede cambiar el modo en que su organización recibe las actualizaciones de Microsoft 365 mediante los siguientes pasos. Debe ser un administrador global de Microsoft 365 para participar.
  
> [!IMPORTANT]
> Los cambios siguientes pueden tardar hasta 24 horas en surtir efecto en Microsoft 365. Si opta por una opción distinta a la versión dirigida después de activarlo, puede que los usuarios pierdan el acceso a características que todavía no han alcanzado la versión programada. 
  
1. En el centro de administración, vaya a **Settings** > configuración y **, en**la pestaña **perfil** de la organización, elija **Opciones de lanzamiento**.

5. Para deshabilitar la versión dirigida, seleccione **versión estándar**y, a continuación, seleccione **Guardar cambios**. 
    
6. Para habilitar la versión dirigida para todos los usuarios de su organización, seleccione **versión dirigida para todos**y, a continuación, seleccione **Guardar cambios**. 
    
7. Para habilitar la versión dirigida para algunas personas de su organización, seleccione **versión dirigida para los usuarios seleccionados**y, a continuación, seleccione **Guardar cambios**. 
    
8. Elija **Seleccionar usuarios** para agregar usuarios de uno en uno o **cargar usuarios** para agregarlos de forma masiva.
    
9. Cuando haya terminado de agregar usuarios, seleccione **Guardar cambios**.



## <a name="get-the-targeted-release-version-of-office"></a>Obtener la versión de lanzamiento de Office dirigida

Para instalar una compilación de la versión dirigida de Office, [siga estos pasos](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). De esta manera obtendrá acceso previo a las nuevas características de Office 2016 para escritorios de Windows.
  
## <a name="learn-more"></a>Más información

Descubra cómo [administrar mensajes](https://docs.microsoft.com/office365/admin/manage/message-center) en el [centro de mensajes de Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obtener notificaciones sobre próximas actualizaciones y versiones de Microsoft 365.
