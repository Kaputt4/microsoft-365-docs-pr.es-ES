---
title: Solución de problemas Microsoft 365 la integración con ServiceNow
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
ms.openlocfilehash: 24813fe0d0705d9404fa465420e3b0344f43f953
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662145"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>Solución de problemas Microsoft 365 la integración con ServiceNow

| \#  | Problema  | Acción diagnóstico     |
|-----|--------------------------------|----------------------|
| 1   | No se puede ver la **Microsoft 365 de soporte** técnico                                                                                                                                                                                    | Comprobar la vista actual y **todos los registros del** sistema con el filtro x &gt;  \_ mioms \_ m365 \_ assit                        |
| 2   | Seleccione **soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídales que completen los pasos de configuración de la aplicación".                                                                      | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 3   | Seleccione **soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídales que completen el paso de configuración final de la aplicación".                                                                | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 4    | Escriba el problema en el cuadro de búsqueda y seleccione Soluciones recomendadas de **Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".                                   | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 5   | Escriba problema en el cuadro de búsqueda y seleccione Soluciones recomendadas de **Microsoft** pero obtenga el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".                                 | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 6    | Selecciona Póngase en contacto con el soporte técnico de **Microsoft,** pero recibe el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete los pasos de configuración de la aplicación".                                                                       | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 7    | Selecciona Póngase en contacto con el soporte técnico de **Microsoft,** pero recibe el error "Póngase en contacto con el administrador de ServiceNow y pídale que complete el paso de configuración final de la aplicación".                                                                 | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 8    | Seleccione **Póngase en contacto con** el soporte técnico de Microsoft pero obtenga el error "{EmailAddress} no es una cuenta de administrador Microsoft 365 válida. Necesita privilegios Microsoft 365 administrador para abrir una solicitud de servicio. En la aplicación, vincula la cuenta de administrador". | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 9    | Seleccionar **soluciones recomendadas de Microsoft,** pero no aparece nada                                                                                                                                                            | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com |
| 10  | Seleccione **Soluciones recomendadas de Microsoft pero** obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".                                                                                                                                     | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 11  | Escriba problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft,** pero no aparece nada                                                                                                                             | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com |
| 12   | Escriba problema en el cuadro de búsqueda y seleccione **Soluciones recomendadas de Microsoft** pero obtenga el error "Póngase en contacto con el soporte técnico de la aplicación".                                                                                                      | Compruebe el mensaje de error en la parte superior del formulario y **Registros** del sistema Todo con &gt;  filtro x \_ mioms \_ m365 \_ assit     |
| 13  | El usuario selecciona **Póngase en contacto con el soporte técnico de Microsoft,** pero no ocurre nada                                                                                                                                                            | Comprobar **registros del sistema: registros HTTP salientes** con login.microsoftonline.com y connector.rave.microsoft.com |
| 14   | No se puede ver la solución recomendada por Microsoft después de volver a abrir el incidente                                                                                                                                                      | Comprobar **registros del** sistema &gt; **todo** con filtro x \_ mioms \_ m365 \_ assit                                              |
| 15   | No se pueden ver casos de Microsoft al volver a abrir el incidente que se transfirió al soporte técnico de Microsoft                                                                                                                            | Comprobar **registros del** sistema &gt; **todo** con filtro x \_ mioms \_ m365 \_ assit                                              |
| 16  | No se pueden guardar los detalles del vale, recibe el error "No se pueden guardar los detalles del vale. Póngase en contacto con el soporte técnico de la aplicación".                                                                                                                          | Comprobar el mensaje de error en la parte superior del formulario                                                                            |
