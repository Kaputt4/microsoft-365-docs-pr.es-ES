---
title: Agregar un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Es posible que su organización necesite varios dominios para que los clientes puedan encontrarlo. Obtenga información sobre cómo agregar otro dominio a la suscripción.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706435"
---
# <a name="add-another-domain"></a>Agregar otro dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Es posible que su empresa necesite varios nombres de dominio para fines diferentes. Por ejemplo, es posible que desee agregar una ortografía diferente del nombre de la compañía porque los clientes ya lo están usando y sus comunicaciones no le han llegado.

## <a name="try-it"></a>¿Se atreve?

1. En el centro Microsoft 365 administración, elija **Configurar**.
1. En **Obtener la configuración del dominio personalizado,** seleccione **Ver**.
1. Elija **Administrar** y, a **continuación, Agregar dominio**.
1. Escriba el nuevo nombre de dominio que desea agregar y, a continuación, seleccione **Siguiente**.
1. Inicie sesión en el registrador de dominio, en este caso GoDaddy y, a continuación, **seleccione Siguiente**.
1. Si se le solicita, inicie sesión en el registrador y, a continuación, elija **Autorizar**.
1. Elija **Agregar los registros DNS para mí** y, a continuación, seleccione **Siguiente**.
1. Elija los servicios para el nuevo dominio y desactive las casillas para los servicios que se administrarán mediante un dominio diferente. Por ejemplo, si solo desea usar el nuevo dominio para el correo electrónico,  elija **Exchange** y desactive las casillas para Skype Empresarial y **Administración de dispositivos móviles para Office 365**.
1. Seleccione **Siguiente**, **Autorizar**, **Siguiente** y, a continuación, **Finalizar**. Se ha agregado el nuevo dominio.

Para recibir correo electrónico en el nuevo dominio, deberá agregar un nuevo alias de correo electrónico para cada usuario:

1. Seleccione **Usuarios**, **Usuarios activos** y, a continuación, seleccione el usuario al que se le asignará el nuevo alias.
1. Elija **Administrar alias de correo** electrónico **y, a continuación, Agregar un alias**.
1. Escriba el nombre de usuario y, a continuación, elija el nuevo dominio de la lista desplegable.
1. Seleccione **Guardar cambios** y, a continuación, cierre la ventana.
1. Repita estos pasos para cada usuario que debe recibir correo electrónico en el nuevo dominio.

## <a name="related-content"></a>Contenido relacionado

[Agregar un dominio a Microsoft 365](../admin/setup/add-domain.md) (artículo)\
[Agregar registros DNS para conectar el dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (artículo)\
[Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (artículo)\
[Preguntas más frecuentes sobre dominios](../admin/setup/domains-faq.yml) (artículo)