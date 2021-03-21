---
title: Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta Guía del laboratorio de pruebas para crear y usar etiquetas de retención en documentos de su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919193"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del laboratorio de pruebas se puede usar para entornos de prueba de Microsoft 365 para empresas y office 365 Enterprise.*

En este artículo se describe cómo configurar la clasificación de datos mediante etiquetas de retención en el entorno de prueba de Microsoft 365 para empresas.

Clasificar datos en el entorno de prueba implica tres fases:
- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Crear etiquetas de retención](#phase-2-create-retention-labels)
- [Fase 3: Aplicar etiquetas de retención a documentos](#phase-3-apply-retention-labels-to-documents)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para](../downloads/Microsoft365EnterpriseTLGStack.pdf)enterprise Test Lab Guide Stack .
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si solo desea configurar etiquetas de retención de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea configurar etiquetas de retención en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de etiquetas de retención no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: Crear etiquetas de retención

En esta fase, cree las etiquetas de retención para los diferentes niveles de retención de carpetas de documentos de SharePoint Online:

1. Inicie sesión en el [Centro de seguridad de Microsoft 365](https://security.microsoft.com/homepage) con su cuenta de administrador global.
1. En la **pestaña Inicio - Seguridad de Microsoft 365** del explorador, seleccione **Etiquetas de** retención de  >  **clasificación.**
1. Seleccione **Crear una etiqueta**.
1. En el **panel Nombre de la etiqueta,** escriba Public **interno** en Nombre de la **etiqueta** y, a continuación, **seleccione Siguiente**.
1. En el **panel Descriptores de plan de archivos,** seleccione **Siguiente**.
1. En el **panel Configuración de** etiqueta, si es necesario, establezca **Retención** en **On** y, a continuación, seleccione **Siguiente**.
1. En el **panel Revisar la configuración,** seleccione **Crear la etiqueta**.
1. Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:
  - Private
  - Confidencial
  - Extremadamente confidencial
1. En el **panel Etiquetas de** retención, seleccione **Publicar etiquetas**.
1. En el **panel Elegir etiquetas para publicar,** seleccione **Elegir etiquetas para publicar**.
1. En el **panel Elegir etiquetas,** seleccione **Agregar** y seleccione las cuatro etiquetas.
1. Seleccione **Agregar** y, a continuación, **Seleccione Listo**.
1. En el **panel Elegir etiquetas para publicar,** seleccione **Siguiente**.
1. En el **panel Elegir ubicaciones,** seleccione **Siguiente**.
1. En el **panel Nombre de la directiva,** escriba **Organización** de ejemplo en **Nombre** y, a continuación, **seleccione Siguiente**.
1. En el **panel Revisar la configuración,** seleccione **Publicar etiquetas**.
 
Las etiquetas de retención pueden tardar unos minutos en publicarse.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: Aplicar etiquetas de retención a documentos

En esta fase, se detecta el comportamiento predeterminado de la etiqueta de retención de los archivos de la carpeta Documentos de un sitio de SharePoint Online y se cambia manualmente la etiqueta de retención de un documento.

En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:
  
1. Con una instancia privada del explorador, inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con su cuenta de administrador global.
1. En la lista de iconos, seleccione **SharePoint**.
1. En la nueva **pestaña de SharePoint** del explorador, seleccione **Crear sitio**.
1. En la página **Crear un sitio**, seleccione **Sitio de grupo**.
1. En el **cuadro Nombre del sitio del** equipo, escriba **SensitiveFiles**.
1. En el **cuadro Descripción del sitio de** grupo, escriba Sitio de **SharePoint para archivos confidenciales.**
1. En **Configuración de privacidad,** **seleccione Privado: solo los miembros** pueden tener acceso a este sitio y, a continuación, **seleccione Siguiente**.
1. En el **panel ¿A quién desea agregar?,** seleccione **Finalizar**.
    
A continuación, configure la carpeta Documentos del sitio de grupo SensitiveFiles para la etiqueta de retención Confidencial.
  
1. En la **pestaña SensitiveFiles** del explorador, seleccione **Documentos**.
1. Seleccione el **icono Configuración** y, a continuación, seleccione Configuración **de biblioteca.**
1. En **Permisos y administración,** seleccione **Aplicar etiqueta a los elementos de esta lista o biblioteca.** Si esta opción no aparece, las etiquetas de retención aún no se publican. Pruebe este paso más adelante.
1. En **Configuración-Aplicar etiqueta**, seleccione **Confidencial** en el cuadro desplegable y, a continuación, **seleccione Guardar**.

A continuación, cree un nuevo documento en el sitio SensitiveFiles y cambie su etiqueta de retención.
    
1. En la carpeta documentos, seleccione **Nuevo**  >  **documento de Word**.
1. Escriba texto en el documento en blanco. Espere a que se guarde el texto.
1. En la barra de menús, seleccione **Documentos compartidos**.
1. Junto al nombre **Document.docx** archivo, seleccione los puntos suspensivos verticales y, a continuación, **seleccione Detalles**.
1. En el panel derecho, en la sección **Propiedades,** en **Aplicar** etiqueta de retención, tenga en cuenta que el documento se ha aplicado automáticamente la **etiqueta** de retención confidencial.
1. Haga clic en **Editar todo**.
1. En el **Document.docx,** en **Aplicar** etiqueta de retención, seleccione la **etiqueta Extremadamente** confidencial y, a continuación, **seleccione Guardar**.

## <a name="next-step"></a>Paso siguiente

Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en el entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)