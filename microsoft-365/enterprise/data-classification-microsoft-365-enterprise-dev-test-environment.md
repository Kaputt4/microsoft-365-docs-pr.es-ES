---
title: Clasificación de datos para su Microsoft 365 entorno de prueba empresarial
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta Guía del laboratorio de pruebas para crear y usar etiquetas de retención en documentos Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: a39661da9436473da9e89330ff15d0a43d19db51
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218587"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Clasificación de datos para su Microsoft 365 entorno de prueba empresarial

*Esta Guía del laboratorio de pruebas se puede usar tanto Microsoft 365 entornos de prueba empresariales como Office 365 Enterprise de prueba.*

En este artículo se describe cómo configurar la clasificación de datos mediante etiquetas de retención Microsoft 365 entorno de prueba empresarial.

Clasificar datos en el entorno de prueba implica tres fases:
- [Fase 1: Crear su Microsoft 365 entorno de prueba empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Crear etiquetas de retención](#phase-2-create-retention-labels)
- [Fase 3: Aplicar etiquetas de retención a documentos](#phase-3-apply-retention-labels-to-documents)

![Guías del laboratorio de pruebas para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear su Microsoft 365 entorno de prueba empresarial

Si solo desea configurar etiquetas de retención de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea configurar etiquetas de retención en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de etiquetas de retención no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: Crear etiquetas de retención

En esta fase, cree las etiquetas de retención para los diferentes niveles de retención para SharePoint carpetas de documentos en línea:

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">centro Microsoft 365 seguridad con</a> su cuenta de administrador global.
1. En la **pestaña Inicio- Microsoft 365 seguridad** del explorador, seleccione **Etiquetas de** retención de  >  **clasificación.**
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

En esta fase, detectará el comportamiento predeterminado de la etiqueta de retención de los archivos de la carpeta Documentos de un sitio de SharePoint Online y cambiará manualmente la etiqueta de retención de un documento.

En primer lugar, cree un sitio de grupo SharePoint nivel confidencial:
  
1. Con una instancia privada del explorador, inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con su cuenta de administrador global.
1. En la lista de iconos, seleccione **SharePoint**.
1. En la nueva **SharePoint** en el explorador, seleccione **Crear sitio**.
1. En la página **Crear un sitio**, seleccione **Sitio de grupo**.
1. En el **cuadro Nombre del sitio del** equipo, escriba **SensitiveFiles**.
1. En el **cuadro Descripción del sitio de** grupo, escriba SharePoint sitio para archivos **confidenciales**.
1. En **Configuración de privacidad,** **seleccione Privado: solo los miembros** pueden tener acceso a este sitio y, a continuación, **seleccione Siguiente**.
1. En el **Quién ¿desea agregar? panel,** seleccione **Finalizar**.
    
A continuación, configure la carpeta Documentos del sitio de grupo SensitiveFiles para la etiqueta de retención Confidencial.
  
1. En la **pestaña SensitiveFiles** del explorador, seleccione **Documentos**.
1. Seleccione el **Configuración** y, a continuación, seleccione **Configuración de biblioteca**.
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

## <a name="see-also"></a>Consulte también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)