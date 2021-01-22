---
title: Buscar y corregir problemas después de agregar el dominio o los registros DNS
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Aprenda a realizar un seguimiento de los problemas que se encuentran al configurar un dominio personalizado al asegurarse de que los registros DNS están configurados correctamente.
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926395"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Buscar y corregir problemas después de agregar el dominio o los registros DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Configurar el dominio para que funcione con Microsoft 365 puede ser complicado. El sistema DNS puede ser un poco enrevesado y la configuración DNS de su dominio afecta a importantes actividades empresariales, como el correo electrónico.

> [!NOTE]
> Puede comprobar si hay problemas con su dominio comprobando su estado. Vaya a **Dominios**  >  **de instalación** y vea las notificaciones en la **columna** Estado. Si ves un problema, selecciona Más acciones (tres puntos) y, a continuación, elige **Comprobar estado.** En el panel que se abre se describen los problemas que se produzcan con el dominio.
  
## <a name="whats-going-on"></a>¿Qué sucede?

- [¿No puede comprobar su dominio?](#cant-verify-your-domain)
    
- [¿Outlook no funciona?](#outlook-isnt-working)
    
- [¿El correo electrónico de todos los usuarios cambió a Microsoft 365 y solo quería que cambiara su correo electrónico?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [¿No se puede confirmar el estado de la cuenta educativa o sin ánimo de lucro?](#cant-confirm-non-profit-or-school-account-status)

- [¿Los servicios no funcionan con su dominio?](#services-not-working-with-your-domain)
    
- [¿El acceso a su sitio web no funciona?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>¿No puede comprobar su dominio?
<a name="BKMK_verify"> </a>

Hay algunas razones comunes por las que la comprobación del dominio puede no funcionar según lo esperado:
  
1. **El valor del registro de comprobación no es del todo correcto.** Compruebe que ha copiado y pegado el valor exacto en el registro de comprobación TXT en su host DNS. Uno de los problemas habituales es no incluir la parte de "MS=" del registro. ¡También la necesitamos! 
    
2. **No se ha guardado el registro.** En algunos hosts DNS, tiene que llevar a cabo un paso adicional para guardar el archivo de zona (donde se almacena el registro DNS), de modo que se actualice a través de Internet. Asegúrese de que ha guardado los cambios para que Microsoft 365 pueda ver y comprobar el registro. 
    
3. **El registro no se ha actualizado a través de Internet.** Normalmente, solo tarda unos minutos en poder ver el nuevo registro, pero en ocasiones puede tardar hasta unas horas. 
    
## <a name="outlook-isnt-working"></a>¿Outlook no funciona?
<a name="BKMK_OutlookBroken"> </a>

Si ha configurado correctamente el registro MX y otros registros DNS de su dominio pero el correo electrónico no funciona, podemos ayudarle a [solucionar los problemas relacionados con Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>¿El correo electrónico de todos los usuarios cambió a Microsoft 365 y solo quería que cambiara su correo electrónico?
<a name="BKMK_EmailSwitched"> </a>

Cuando agrega su dominio a Microsoft 365, normalmente el registro MX de su dominio se actualiza (por usted o Microsoft 365) para que apunte a Microsoft 365 y todo el correo electrónico enviado a ese dominio empezará a llegar a Microsoft 365. Asegúrese de que ha creado buzones en Microsoft 365 para todos los usuarios que tienen correo electrónico en su dominio ANTES de cambiar el registro MX.
  
¿Qué ocurre si no desea mover el correo electrónico de todos los usuarios de su dominio a Microsoft 365? Puede tomar medidas para [pilotar Microsoft 365 con solo unas pocas direcciones de correo electrónico en su lugar.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>¿No se puede confirmar el estado de la cuenta educativa o sin ánimo de lucro?
<a name="BKMK_validateAcct"> </a>

Hay un par de escenarios en los que solo necesita comprobar el dominio de su organización y no configurar ningún servicio. Por ejemplo, para demostrar a Microsoft 365 que su organización cumple los requisitos para una suscripción educativa.
  
Consulte las instrucciones de Comprobar su dominio de [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) para demostrar la propiedad, la organización sin ánimo de lucro o el estado educativo, o para activar Yammer para asegurarse de que ha completado todos los pasos necesarios. Es un poco diferente para cada situación. 
  
## <a name="services-not-working-with-your-domain"></a>¿Los servicios no funcionan con su dominio?
<a name="BKMK_Test"> </a>

Podemos ayudarle a localizar los problemas de configuración DNS de su dominio. El solucionador de problemas de dominios de Microsoft 365 le mostrará todos los registros que necesiten corregirse y exactamente en qué deben establecerse los registros. 

> [!TIP]
> ¿Ha configurado DNS correctamente pero el correo electrónico no funciona en la versión de escritorio de Outlook? Consulte los diferentes escenarios de flujo de correo que puede tener con [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) para asegurarse de que tiene todo configurado correctamente para su empresa. O bien, obtenga más ayuda para solucionar problemas con el correo electrónico aquí: [Solucionar problemas de Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>¿El acceso a su sitio web no funciona?
<a name="BKMK_Website"> </a>

Si ha corregido cualquier problema de DNS y sigue teniendo dificultades, pruebe los siguientes procedimientos.
  
- Los usuarios no pueden obtener acceso al sitio web en www.mydomain.com: [localizar problemas de sitio web](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- No puede actualizar el registro A o el registro CNAME para que apunten a su sitio web: actualizar registros DNS personalizados [en Microsoft 365](../dns/add-or-edit-custom-dns-records.md)

## <a name="related-content"></a>Contenido relacionado

[Solución de problemas: auditar datos sobre el cambio de dominio comprobado](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
