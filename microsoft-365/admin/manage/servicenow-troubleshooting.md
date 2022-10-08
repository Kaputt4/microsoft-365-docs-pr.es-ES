---
title: Solución de problemas con la integración de soporte técnico con ServiceNow de Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Guía de instalación y configuración de aplicaciones con ámbito certificado para ServiceNow.
ms.openlocfilehash: 66cab6fe21f39b4db2207d78b8b0b1239df2b0d1
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68208400"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>Solución de problemas con la integración de soporte técnico con ServiceNow de Microsoft 365

| \#  | Problema  | Acción de diagnóstico     |
|-----|--------------------------------|----------------------|
| 1   | No se puede ver la pestaña **compatibilidad con Microsoft 365**                                                                                                                                                                                    | Compruebe la vista actual y **los registros** &gt; del sistema **todos** con el filtro x\_mioms\_m365\_assit                        |
| 2   | Seleccione **las soluciones recomendadas de Microsoft** , pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".                                                                      | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 3   | Seleccione **las soluciones recomendadas por Microsoft** , pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".                                                                | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 4   | Escriba el problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** , pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".                                   | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 5   | Escriba el problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** , pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".                                 | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 6   | Seleccione **Ponerse en contacto con el soporte técnico de Microsoft**, pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".                                                                       | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 7    | Seleccione **Ponerse en contacto con el soporte técnico de Microsoft**, pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".                                                                 | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 8    | Seleccione **Ponerse en contacto con soporte técnico de Microsoft** , pero obtenga el error "{EmailAddress} no es una cuenta de administrador válida de Microsoft 365. Necesita privilegios de administrador de Microsoft 365 para abrir una solicitud de servicio. En la aplicación, vincule la cuenta de administrador." | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 9    | Seleccionar **soluciones recomendadas de Microsoft** , pero no aparece nada                                                                                                                                                            | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com de filtro y connector.rave.microsoft.com |
| 10  | Seleccione **soluciones recomendadas de Microsoft** , pero obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".                                                                                                                                     | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 11  | Escriba el problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** , pero no aparece nada.                                                                                                                             | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com de filtro y connector.rave.microsoft.com |
| 12   | Escriba el problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** , pero obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".                                                                                                      | Compruebe el mensaje de error en la parte superior del formulario y **registros** &gt; del sistema **todo** con el filtro x\_mioms\_m365\_assit     |
| 13   | El usuario selecciona **Ponerse en contacto con el soporte técnico de Microsoft**, pero no ocurre nada.                                                                                                                                                            | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com de filtro y connector.rave.microsoft.com |
| 14   | No se puede ver la solución recomendada por Microsoft después de volver a abrir el incidente                                                                                                                                                      | Comprobar **todos los registros** &gt; del sistema con  el filtro x\_mioms\_m365\_assit                                              |
| 15   | No se pueden ver los casos de Microsoft al volver a abrir el incidente que se transfirió al soporte técnico de Microsoft.                                                                                                                            | Comprobar **todos los registros** &gt; del sistema con  el filtro x\_mioms\_m365\_assit                                              |
| 16   | No se pueden guardar los detalles del vale, se produce el error "No se pueden guardar los detalles del vale. Póngase en contacto con el soporte técnico de la aplicación."                                                                                                                          | Compruebe el mensaje de error en la parte superior del formulario.                                                                            |
