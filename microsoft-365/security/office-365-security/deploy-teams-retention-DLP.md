---
title: Protección de los archivos de los equipos con etiquetas de retención y DLP
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Resumen: Aplique etiquetas de retención y directivas de prevención de pérdida de datos (DLP) a los archivos de los equipos con distintos niveles de protección de la información.'
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083419"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a>Protección de los archivos de los equipos con etiquetas de retención y DLP

 
Siga los pasos de este artículo para diseñar e implementar etiquetas de retención y directivas de prevención de pérdida de datos (DLP) para equipos de línea base, confidenciales y extremadamente confidenciales y sus correspondientes sitios de SharePoint subyacentes. Para más información sobre estos tres niveles de protección, vea [Proteger archivos en Microsoft Teams](secure-files-in-teams.md).
  
## <a name="how-this-works"></a>Cómo funciona

1. Crear las etiquetas de retención deseadas y publicarlas. Su publicación puede tardar hasta 12 horas.
2. En los sitios de SharePoint subyacentes de su elección, edite la configuración de la biblioteca de documentos para aplicar las etiquetas de retención deseadas a los elementos de la biblioteca.
3. Cree directivas DLP que actúen en función de las etiquetas de retención.

Cuando los usuarios agregan un documento a la biblioteca del sitio de SharePoint subyacente, el documento recibirá la etiqueta de retención asignada de forma predeterminada. Los usuarios pueden cambiar la etiqueta, si fuera necesario. Cuando un usuario comparte un documento fuera de la organización, DLP comprobará si se le ha asignado una etiqueta y tomará medidas si una directiva DLP coincide con la etiqueta. DLP buscará otras coincidencias de directivas, como la protección de archivos con números de tarjetas de crédito si se ha configurado este tipo de directiva. 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a>Etiquetas de retención de los sitios de SharePoint subyacentes

Las fases para crear y asignar etiquetas de retención a sitios de SharePoint subyacentes son tres.
  
### <a name="step-1-determine-the-retention-label-names"></a>Paso 1: Determinar los nombres de etiqueta de retención

En esta fase se determinan los nombres de las etiquetas de retención de los cuatro niveles de protección de la información aplicados a los sitios de SharePoint subyacentes. En la siguiente tabla se indican los nombres recomendados de cada nivel.
  
|**Nivel de protección de sitios de SharePoint subyacentes**|**Nombre de etiqueta**|
|:-----|:-----|
|Base de referencia-Público  <br/> |Interno público  <br/> |
|Base de referencia-Privado  <br/> |Private  <br/> |
|Confidencial  <br/> |Confidencial  <br/> |
|Extremadamente confidencial  <br/> |Extremadamente confidencial  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a>Paso 2: Crear las etiquetas de retención

En esta fase se crean y luego se publican las etiquetas determinadas para los diferentes niveles de protección de la información.
  
1. Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con una cuenta que tenga el rol de administrador de seguridad o administrador de la empresa.
    
2. En la pestaña **Inicio: Cumplimiento de Microsoft 365** del explorador, haga clic en **Clasificaciones > Etiquetas**.
    
3. Haga clic en **Etiquetas de retención > Crear una etiqueta**.
    
4. En el panel **Asignar un nombre a la etiqueta**, escriba el nombre de la etiqueta y una descripción para administradores y usuarios, después, haga clic en **Siguiente**.

5. En el panel **Descriptores del plan de archivos**, rellene lo que sea necesario y, a continuación, haga clic en **Siguiente**.
    
6. En el panel **Configuración de etiqueta**, si es necesario, marque **Retención** como **Activado** y establezca la configuración de retención. Haga clic en **Siguiente**.
    
7. En el panel **Revise su configuración**, haga clic en **Crear la etiqueta**.
    
8. Para las otras etiquetas, haga clic en **Crear una etiqueta** y, después, repita los pasos del 3 al 7 de este procedimiento según sea necesario.
    

### <a name="publish-your-new-labels"></a>Publicar las nuevas etiquetas

Luego siga estos pasos para publicar las nuevas etiquetas de retención.
  
1. En el panel **Etiquetas**, haga clic en la pestaña **Retención** y, después, haga clic en **Publicar etiquetas**.
    
2. En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.
    
3. En el panel **Elección de etiquetas**, haga clic en **Agregar**, seleccione las cuatro etiquetas y haga clic en **Agregar**.
    
4. Haga clic en **Listo**.
    
5. En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.
    
6. En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.
    
7. En el panel **Escriba un nombre para la directiva**, escriba un nombre para el conjunto de etiquetas en **Nombre** y haga clic en **Siguiente**.
    
8. En el panel **Revise su configuración**, haga clic en **Publicar etiquetas** y luego en **Cerrar**.

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a>Paso 3: Aplicar las etiquetas de retención a los sitios de SharePoint subyacentes

Siga estos pasos para aplicar las etiquetas de retención a las carpetas de documentos de los sitios de SharePoint subyacentes.
  
1.  En el equipo, haga clic en **Archivos** y, después, en **Abrir en SharePoint**.

2. En la nueva pestaña del sitio de SharePoint del explorador, haga clic en **Documentos**.
    
3. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
    
4. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
5. En **Configuración-Aplicar etiqueta**, seleccione la etiqueta de retención adecuada y haga clic en **Guardar**.
    
6. Cierre la pestaña del sitio de SharePoint.
    
7. Repita los pasos del 1 al 6 para asignar etiquetas de retención a otros sitios de SharePoint subyacentes.
    
Este es el resultado de la configuración.
  
![Etiquetas de retención de los cuatro tipos de sitios de SharePoint subyacentes.](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a>Directivas DLP de los sitios de SharePoint subyacentes

Siga estos pasos para configurar una directiva DLP que notifique a los usuarios cada vez que compartan un documento en un sitio de SharePoint subyacente fuera de la organización.

1. Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) con una cuenta que tenga el rol de administrador de seguridad o administrador de la empresa.
    
2. En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.
    
3. En el panel **Inicio > Prevención de pérdida de datos**, haga clic en **Crear una directiva**.
    
4. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
    
5. En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel confidencial en **Nombre** y haga clic en **Siguiente**.
    
6. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.
    
7. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.
    
8. En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Editar**.
    
9. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.
    
10. En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.
    
11. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
    
12. En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Siguiente**.

13. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
    
14. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
    
15. En el cuadro de texto, escriba o pegue una de las siguientes sugerencias:
    
  - Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
  - Los archivos extremadamente confidenciales están protegidos con cifrado. Solo pueden leerlos aquellos usuarios externos a los que su departamento de TI les ha concedido permiso para acceder a los archivos.
    
    Otra opción es escribir o pegar una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.
    
16. Haga clic en **Aceptar**.
    
17. En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.
    
18. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.
    
19. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.
    
Esta es la configuración resultante de los equipos confidenciales.
  
![Directiva DLP de equipos confidenciales que usan la etiqueta de retención confidencial](../../media/retention-labels-sensitive-dlp.png)
  
Después, siga estos pasos para configurar una directiva DLP que bloquee a los usuarios cada vez que compartan un documento en un sitio de SharePoint subyacente fuera de la organización.
  
1. En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.
    
2. En el panel **Prevención de pérdida de datos**, haga clic en **Crear una directiva**.
    
3. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
    
4. En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel extremadamente confidencial en **Nombre** y haga clic en **Siguiente**.
    
5. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.
    
6. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.
    
7. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.
    
8. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.
    
9. En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.
    
10. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
    
12. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.
    
13. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
    
14. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
    
15. En el cuadro de texto, escriba o pegue lo siguiente:
    
  - Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
    
    O bien escriba o pegue una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.
    
16. Haga clic en **Aceptar**.
    
17. En el panel **¿Qué desea hacer si detectamos información confidencial?**, en **Detectar cuando una cantidad específica de información confidencial se comparte al mismo tiempo**, haga clic en **Restringir acceso o encriptar el contenido**, y luego haga clic en **Siguiente**.
    
18. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.
    
19. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.
    
Esta es la configuración resultante del equipo extremadamente confidencial.
  
![Directiva DLP de un equipo de confidencialidad extrema que usa la etiqueta de retención extremadamente confidencial](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a>Siguiente paso

[Proteger los archivos de los equipos con etiquetas de confidencialidad](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a>Vea también

[Proteger los archivos en Microsoft Teams](secure-files-in-teams.md)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


