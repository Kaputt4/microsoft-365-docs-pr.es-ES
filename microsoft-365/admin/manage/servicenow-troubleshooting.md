---
title: Solución de problemas con la integración de soporte técnico con ServiceNow de Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Guía de configuración y instalación de aplicaciones certificadas con ámbito para ServiceNow.
ms.openlocfilehash: bac3981b728ac997839e7ac99a9411a8da244add
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324947"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>Solución de problemas con la integración de soporte técnico con ServiceNow de Microsoft 365

| \#  | Problema  | Acción diagnóstico     |
|-----|--------------------------------|----------------------|
| 1   | No se puede ver la **Microsoft 365 de** soporte técnico                                                                                                                                                                                    | Comprobar la vista actual y **todos los registros del** &gt; **sistema** con el filtro xmiomsm365assit\_\_\_                        |
| 2   | Seleccione **soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídales que completen los pasos de configuración de la aplicación".                                                                      | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 3   | Seleccione **soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídales que completen el paso de configuración final de la aplicación".                                                                | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 4   | Escriba el problema en el cuadro de búsqueda y seleccione Soluciones recomendadas de **Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".                                   | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 5   | Escriba problema en el cuadro de búsqueda y seleccione Soluciones recomendadas de **Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".                                 | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 6    | Selecciona **Póngase en contacto** con el soporte técnico de Microsoft, pero recibe el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".                                                                       | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 7    | Selecciona **Póngase en contacto** con el soporte técnico de Microsoft, pero recibe el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".                                                                 | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 8    | Seleccione **Póngase en contacto con el soporte** técnico de Microsoft pero obtenga el error "{EmailAddress} no es una cuenta Microsoft 365 administrador. Necesita privilegios Microsoft 365 administrador para abrir una solicitud de servicio. En la aplicación, vincula la cuenta de administrador". | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 9    | Seleccionar **soluciones recomendadas de Microsoft** , pero no aparece nada                                                                                                                                                            | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com |
| 10  | Seleccione **Soluciones recomendadas de Microsoft pero** obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".                                                                                                                                     | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 11  | Escriba problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** , pero no aparece nada                                                                                                                             | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com |
| 12   | Escriba problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".                                                                                                      | Compruebe el mensaje de error en la parte superior del formulario y **Registros** &gt; del sistema **Todo** con el filtro xmiomsm365assit\_\_\_     |
| 13  | El usuario selecciona **Póngase en contacto con el soporte técnico de Microsoft**, pero no pasa nada                                                                                                                                                            | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com |
| 14   | No se puede ver la solución recomendada por Microsoft después de volver a abrir el incidente                                                                                                                                                      | Comprobar **registros del** &gt; **sistema todo** con el filtro xmiomsm365assit\_\_\_                                              |
| 15   | No se pueden ver casos de Microsoft al volver a abrir el incidente que se transfirió al soporte técnico de Microsoft                                                                                                                            | Comprobar **registros del** &gt; **sistema todo** con el filtro xmiomsm365assit\_\_\_                                              |
| 16  | No se pueden guardar los detalles del vale, recibe el error "No se pueden guardar los detalles del vale. Póngase en contacto con el soporte técnico de la aplicación".                                                                                                                          | Comprobar el mensaje de error en la parte superior del formulario                                                                            |
