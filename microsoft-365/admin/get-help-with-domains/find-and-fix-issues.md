---
title: Buscar y corregir problemas después de agregar el dominio o los registros DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Aprenda a realizar un seguimiento de los problemas que se produzcan al configurar un dominio personalizado asegurándose de que los registros DNS están configurados correctamente.
ms.openlocfilehash: 13d867559684d80ee5c0e1f7005d1dcaf3b4d611
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628475"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Buscar y corregir problemas después de agregar el dominio o los registros DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Conseguir que su dominio esté configurado para trabajar con Microsoft 365 puede ser un reto. El sistema DNS puede ser un poco enrevesado y la configuración DNS de su dominio afecta a importantes actividades empresariales, como el correo electrónico.

> [!NOTE]
> Puede comprobar si hay problemas en el dominio comprobando su estado. Vaya a **configuración** > de**dominios** y vea las notificaciones en la columna **Estado** . Si ve un problema, seleccione más acciones (tres puntos) y, a continuación, elija **comprobar estado**. El panel que se abre describirá los problemas que se produzcan en su dominio.
  
## <a name="whats-going-on"></a>¿Qué sucede?

- [¿No puede comprobar el dominio?](#cant-verify-your-domain)
    
- [¿Outlook no funciona?](#outlook-isnt-working)
    
- [EL correo electrónico de todos se ha cambiado a Microsoft 365 y solo quiere cambiar el correo electrónico.](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [¿No puede confirmar el estado de la cuenta sin ánimo de lucro o educativa?](#cant-confirm-non-profit-or-school-account-status)

- [¿Los servicios no funcionan con el dominio?](#services-not-working-with-your-domain)
    
- [¿No funciona el acceso al sitio web?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>¿No puede comprobar su dominio?
<a name="BKMK_verify"> </a>

Hay algunas razones comunes por las que la comprobación del dominio puede no funcionar según lo esperado:
  
1. **El valor del registro de comprobación no es del todo correcto.** Compruebe que ha copiado y pegado el valor exacto en el registro de comprobación TXT en su host DNS. Uno de los problemas habituales es no incluir la parte de "MS=" del registro. ¡También la necesitamos! 
    
2. **No se ha guardado el registro.** En algunos hosts DNS, tiene que llevar a cabo un paso adicional para guardar el archivo de zona (donde se almacena el registro DNS), de modo que se actualice a través de Internet. Asegúrese de que ha guardado los cambios para que Microsoft 365 pueda ver y comprobar el registro. 
    
3. **El registro no se ha actualizado a través de Internet.** Normalmente, solo se tarda unos minutos para poder ver el nuevo registro, pero en ocasiones puede tardar varias horas en realizarse. 
    
## <a name="outlook-isnt-working"></a>¿Outlook no funciona?
<a name="BKMK_OutlookBroken"> </a>

Si ha configurado correctamente el registro MX y otros registros DNS de su dominio pero el correo electrónico no funciona, podemos ayudarle a [solucionar los problemas relacionados con Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>EL correo electrónico de todos se ha cambiado a Microsoft 365 y solo quiere cambiar el correo electrónico.
<a name="BKMK_EmailSwitched"> </a>

Cuando se agrega el dominio a Microsoft 365, normalmente se actualiza el registro MX de su dominio (por usted o Microsoft 365) para que apunte a Microsoft 365, y todo el correo electrónico enviado a ese dominio empezará a llegar a Microsoft 365. Asegúrese de que ha creado buzones en Microsoft 365 para todos los usuarios que tengan correo electrónico en su dominio antes de cambiar el registro MX.
  
¿Qué ocurre si no desea mover el correo electrónico de todos los usuarios de su dominio a Microsoft 365? Puede seguir los pasos para probar [Microsoft 365 con unas pocas direcciones de correo electrónico en su lugar](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>¿No puede confirmar el estado de la cuenta sin ánimo de lucro o educativa?
<a name="BKMK_validateAcct"> </a>

Hay un par de escenarios en los que solo tiene que comprobar el dominio de la organización y no configurar ningún servicio. Por ejemplo, para demostrar a Microsoft 365 que su organización es apto para una suscripción escolar.
  
Consulte las instrucciones en [comprobar su dominio de Microsoft 365 para demostrar la propiedad, el estado de ONG o educación, o para activar Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) para asegurarse de que ha completado todos los pasos necesarios. Es un poco diferente para cada situación. 
  
## <a name="services-not-working-with-your-domain"></a>¿Los servicios no funcionan con su dominio?
<a name="BKMK_Test"> </a>

Podemos ayudarle a localizar los problemas de configuración DNS de su dominio. El solucionador de problemas de dominios de Microsoft 365 le mostrará los registros que se deben corregir y exactamente en qué se deben establecer los registros. 

> [!TIP]
> ¿Ha configurado DNS correctamente pero el correo electrónico no funciona en la versión de escritorio de Outlook? Consulte los [diferentes escenarios de flujo de correo que puede tener con Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=787530) para asegurarse de que tiene las cosas correctamente configuradas para su empresa. O bien, obtenga más ayuda para solucionar problemas con el correo electrónico aquí: [Solucionar problemas de Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx). 
  
## <a name="accessing-your-website-isnt-working"></a>¿El acceso a su sitio web no funciona?
<a name="BKMK_Website"> </a>

Si ha corregido cualquier problema de DNS y sigue teniendo dificultades, pruebe los siguientes procedimientos.
  
- Los usuarios no pueden obtener acceso al sitio web en www.mydomain.com: [localizar problemas de sitio web](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- No puede actualizar su registro a o un registro CNAME para que apunten a su sitio web: [actualizar registros DNS personalizados en Microsoft 365](../dns/add-or-edit-custom-dns-records.md)
    
