---
title: Evaluación del impacto de los cambios de configuración de seguridad con el Explorador
description: Ejemplos y tutoriales sobre el uso del Explorador para determinar el impacto de un cambio de control de seguridad (configuración) en Microsoft Defender para Office 365
search.product: ''
ms.service: microsoft-365-security
ms.subservice: mdo
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
search.appverid: met150
ms.openlocfilehash: ea00bf5375d94a3ea7722fcde32c2ada543b187f
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799338"
---
# <a name="assess-the-impact-of-security-configuration-changes-with-explorer"></a>Evaluación del impacto de los cambios de configuración de seguridad con el Explorador

Antes de realizar cambios en la configuración de seguridad, como directivas o reglas de transporte, es importante comprender el impacto de los cambios para que pueda planear y garantizar una interrupción *mínima* en su organización.

Esta guía paso a paso le guiará a través de la evaluación de un cambio y la exportación de los correos electrónicos afectados para su evaluación. El procedimiento se puede aplicar a muchos cambios diferentes, modificando los criterios (filtros) que se usan en el explorador.

## <a name="what-youll-need"></a>Lo que necesitará

- Microsoft Defender para Office 365 Plan 2 (incluido como parte de E5).
- Permisos suficientes (lector de seguridad mínimo necesario para evaluar a través del Explorador de amenazas).
- 5-10 minutos para realizar los pasos siguientes.

## <a name="assess-changing-normal-confidence-phish-delivery-location-to-quarantine-from-the-junk-email-folder"></a>Evaluar el cambio de la ubicación de entrega de phish de confianza normal a la cuarentena (desde la carpeta correo no deseado)

1. **Inicie sesión** en el portal de seguridad y vaya al Explorador (debajo *de Email & Colaboración* en el panel de navegación izquierdo). <https://security.microsoft.com/threatexplorer>
1. Seleccione **Phish** en la selección de la pestaña superior (*Todo el correo electrónico* es la vista predeterminada).
1. Presione el botón **de filtro** (predeterminado en *Sender*) y seleccione **Phish confidence level (Nivel de confianza de Phish**).
1. Seleccione el **nivel de confianza phish** normal.
1. Agregue un **filtro** adicional de **ubicación de entrega original** establecida como **carpeta No deseado**.
1. Presione **Actualizar**. El Explorador ahora se filtra para mostrar todo el correo que se detecta como *phish de confianza normal* y se entrega a la carpeta Junk debido a la configuración de la directiva contra correo no deseado.
1. Si desea dinamizar los datos que se muestran en el gráfico, puede hacerlo mediante la **segmentación de datos de la parte superior izquierda del gráfico (valor predeterminado de *Acción de entrega*),** seleccionando datos útiles como **ip del remitente** o **dominio de remitente** para detectar tendencias y remitentes principales afectados.
1. Debajo de la sección del gráfico, donde se muestran los correos electrónicos afectados, seleccione **Exportar lista de correo electrónico**, que generará un CSV para el análisis sin conexión. **Esta es una lista de los correos electrónicos que se ponerían en cuarentena si la acción de phish se cambiara a Cuarentena (cambio recomendado para valores preestablecidos estándar y estrictos).**

## <a name="assess-removing-a-sender--domain-override-removal"></a>Evaluación de la eliminación de una eliminación de invalidación de dominio o remitente

1. **Inicie sesión en** el portal de seguridad y vaya al **Explorador** (debajo de Email & Colaboración en el panel de navegación izquierdo). <https://security.microsoft.com/threatexplorer>
1. Seleccione **Todo el correo electrónico** si aún no está seleccionado.
1. Presione el botón **de filtro** (predeterminado en *Remitente*) y agregue un filtro de dominio de remitente o remitente y, a continuación, agregue la entrada en la que desea evaluar el impacto de la eliminación.
1. Expanda el intervalo de fechas al máximo & presione **Actualizar** Ahora debería ver el correo que aparece si el dominio remitente o de envío sigue activo en la mensajería de su organización. Si *no* es así, puede que tenga que ajustar el filtro o, como alternativa, ya no recibirá correo de ese dominio o remitente y podrá quitar la entrada de forma segura.
1. Si se muestra correo, esto significa que la entrada sigue siendo un remitente activo. Dinamizar los datos en el gráfico mediante la segmentación de datos (valor predeterminado de *Acción de entrega*) en **Tecnología de detección**.
1. El gráfico debe actualizarse y, si ahora no muestra datos, esto significa que no hemos detectado ninguna amenaza en ninguno de los correos que se mostraron anteriormente, lo que indica que no se necesita una invalidación, ya que no hay ninguna detección que invalidar.
1. Si se muestran datos cuando la **tecnología de detección** segmenta los datos, esto significa que la eliminación de la invalidación *tendría* un impacto en este remitente o dominio debido a que la pila de protección toma medidas.
1. Debe investigar el correo para evaluar si es realmente malintencionado y la entrada se puede quitar, o si es un *falso positivo* y se debe corregir para que ya no se detecte incorrectamente como una amenaza (la autenticación es la principal causa de falsos positivos).

### <a name="further-reading"></a>Lectura adicional

Considere la posibilidad de usar valores preestablecidos seguros [Para asegurarse de que siempre tiene los controles de seguridad óptimos con directivas de seguridad preestablecidas](/microsoft-365/security/office-365-security/step-by-step-guides/ensuring-you-always-have-the-optimal-security-controls-with-preset-security-policies)

También puede administrar problemas de autenticación de correo electrónico con información de [inteligencia de suplantación de identidad](/microsoft-365/security/office-365-security/learn-about-spoof-intelligence)

Obtenga más información sobre la autenticación por correo electrónico [Email autenticación en Exchange Online Protection](/microsoft-365/security/office-365-security/email-validation-and-authentication)
