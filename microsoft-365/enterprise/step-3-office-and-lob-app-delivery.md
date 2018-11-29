---
title: 'Paso 3: Entrega de aplicaciones de Office y de LOB'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre cómo entregar aplicaciones de Office y de LOB.
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871813"
---
# <a name="step-3-office-and-lob-app-delivery"></a>Paso 3: Entrega de aplicaciones de Office y de LOB

Ya está listo para entregar sus aplicaciones de Office y Línea de negocio (LOB). Hay varias maneras de hacerlo, incluidas algunas opciones nuevas e interesantes. Dedique tiempo a revisar y elegir los mejores métodos para sus necesidades actuales.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>Paso 3: Entrega de aplicaciones de Office y de LOB</strong></p>
<p>Asegúrese de que las aplicaciones están empaquetadas y listas para la instalación automática. Obtenga información sobre cómo el empaquetado Hacer clic y ejecutar con Office 365 ProPlus ofrece opciones nuevas para configurar, entregar y mantener actualizadas las aplicaciones de Office.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>Entrega de aplicaciones de Office y de LOB es el tercer paso del ciclo de proceso de implementación recomendado, que abarca las opciones para instalar y administrar Office y LOB. Para que la implementación sea correcta, no omita los primeros dos pasos. Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorios modernos](https://aka.ms/HowToShift).
>

Aunque algunas aplicaciones solo están disponibles como una versión compilada de 32 bits o 64 bits, otras, incluido Office 365 ProPlus, existen como código compilado nativo de 32 bits y 64 bits, y una de las principales decisiones que debe tomar es la versión que se va a implementar. Para aprovechar las ventajas de la potencia de cálculo adicional y la RAM en los dispositivos nuevos, le interesará usar la versión de 64 bits, pero antes tendrá que determinar los posibles problemas de compatibilidad relacionados con los complementos o los archivos. Esto puede requerir visitar de nuevo el Paso 1 Preparación de dispositivos y aplicaciones antes de continuar.

Si no hay nada que lo impida, se recomienda implementar las versiones de 64 bits de todas las aplicaciones, incluido Microsoft Office. Las aplicaciones compiladas nativas de 64 bits ofrecen el mejor rendimiento y son la mejor opción para el futuro.

Existen varios métodos y modelos para instalar aplicaciones en Windows, de modo que vamos a ver las opciones de entrega.

[Administración de aplicaciones de Windows 10](https://docs.microsoft.com/es-ES/windows/application-management/)

## <a name="msi-based-deployments"></a>Implementaciones basadas en MSI

Para las aplicaciones de línea de negocio, es probable que use paquetes basados en MSI o archivos ejecutables, y que instale las aplicaciones como parte de una secuencia de tareas de implementación de sistema operativo. Windows 10 sigue funcionando con estos paquetes.

Las herramientas de implementación de software como System Center Configuration Manager y Microsoft Intune también están optimizadas para la entrega de aplicaciones empaquetadas como MSI. Después de validar las aplicaciones en Windows 10, puede usar System Center Configuration Manager (Rama actual) para la entrega. Si usa el Portal de empresa de Microsoft Intune, puede ampliar la selección de aplicaciones autorizadas por TI disponibles para la organización con el fin de incluir las más recientes y que los usuarios seleccionen ellos mismos las que necesitan.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>Creación de imágenes de equipo

Otro método popular de entrega de aplicaciones es la creación de imágenes de equipo. En este caso, las aplicaciones se instalan bien mediante una secuencia de tareas o de forma manual en un equipo de ejemplo, y después se captura una imagen del sistema con las aplicaciones necesarias preinstaladas. El enfoque de creación de imágenes para crear y capturar puede ahorrar tiempo cuando se aprovisionan equipos nuevos, pero recuerde que los sistemas operativos y las aplicaciones dentro de la imagen pueden quedar obsoletos rápidamente. El modelo de actualización acumulativa de Windows 10 y Office 365 ProPlus ayuda con este problema, pero no lo elimina por completo. Por eso, se recomienda un enfoque de imagen ligera, donde las aplicaciones se instalan desde fuera de la imagen en tiempo de implementación.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

Si quiere incluir Office 365 ProPlus en la imagen, recuerde que se usa una activación basada en el usuario; el administrador del sistema no lo puede activar previamente. Use la herramienta de implementación de Office antes de preinstalar Office en el dispositivo del que se va a crear la imagen y omita el inicio de sesión del usuario. Los usuarios pueden iniciar sesión, asignarse a la activación y aprovechar otras funciones que usan el inicio de sesión en el primer uso.

[Creación de una secuencia de tareas para instalar el sistema operativo](https://docs.microsoft.com/es-ES/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a>Hacer clic y ejecutar 

Office 365 ProPlus se instala mediante Hacer clic y ejecutar, y Hacer clic y ejecutar reemplaza el empaquetado basado en MSI en todas las versiones de la próxima versión de Office 2019 para Windows. Incorpora una serie de ventajas, incluidas instalaciones más rápidas, actualización más rápida y eficaz, y desinstalación más limpia.

Los programas que se entregan a través de Hacer clic y ejecutar se ejecutan en un entorno de aplicación virtual en el equipo y, por tanto, coexisten con otras aplicaciones sin conflictos; también ocupan aproximadamente la mitad del espacio en disco que un paquete basado en MSI. Y como Hacer clic y ejecutar admite el streaming de programas (primero el de las características que más se usan) los usuarios pueden empezar con las aplicaciones de Office en solo unos minutos, en lugar de esperar a que primero se instale completamente. Esto es importante no solo para la implementación inicial; significa que las actualizaciones se pueden transmitir fácilmente en segundo plano con un impacto mínimo para los usuarios.

Si usa System Center Configuration Manager, puede seguir usándolo para la implementación general de Office 365 ProPlus. System Center Configuration Manager (Rama actual) tiene compatibilidad nativa con la Herramienta de personalización de Office actualizada, la personalización de paquetes para Hacer clic y ejecutar en tiempo de instalación y la administración de actualizaciones de software después de la instalación.

[Guía de implementación de Office 365 ProPlus](https://docs.microsoft.com/es-ES/deployoffice/deployment-guide-for-office-365-proplus)

[Desinstalación de versiones de MSI existentes de Office al actualizar a Office 365 ProPlus](https://docs.microsoft.com/es-ES/deployoffice/upgrade-from-msi-version)

[Administración de Office 365 ProPlus con Configuration Manager](https://docs.microsoft.com/es-ES/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[Asignación de aplicaciones de Office 365 a dispositivos Windows 10 con Microsoft Intune](https://docs.microsoft.com/es-ES/intune/apps-add-office365)

## <a name="browser-based-apps"></a>Aplicaciones basadas en el explorador

Hay algunas aspectos que debe considerar para asegurarse de que las aplicaciones basadas el explorador siguen funcionando como se esperaba. Si tiene determinados sitios y aplicaciones web con problemas de compatibilidad conocidos con Microsoft Edge, puede usar la lista de sitios del modo de empresa para que los sitios web se abran de forma automática con Internet Explorer 11.

Además, si sabe que los sitios de la intranet no van a funcionar de forma correcta con Microsoft Edge, puede configurarlos para que se abran de forma automática con Internet Explorer 11. En este proceso se usa un archivo XML para controlar si se utiliza IE11 en cada sitio, mediante la directiva de grupo para aplicar la configuración.

Hasta ahora, hemos analizado métodos de implementación conocidos. Pero hay dos enfoques nuevos de implementación de aplicaciones que es posible que quiera considerar.

[¿Qué es el modo de empresa](https://docs.microsoft.com/es-ES/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas 

Microsoft Store para Empresas proporciona una manera flexible de descubrir, comprar, administrar y distribuir aplicaciones gratuitas y de pago para dispositivos Windows 10 a escala. Como administrador de TI, puede publicar aplicaciones de Microsoft Store concretas, junto con aplicaciones personalizadas propias, en un almacén privado propio, y asignar y volver a usar las licencias según sea necesario. Los usuarios se dirigirán únicamente a este almacén, por lo que solo podrán buscar e instalar las aplicaciones autorizadas.

Las aplicaciones de la tienda se pueden crear de forma nativa como aplicaciones UWP o puede usar el Puente de dispositivo de escritorio para volver a empaquetar las aplicaciones existentes para Microsoft Store y agregar experiencias modernas para Windows 10. Excepto el código que se usa para mejorar las experiencias de Windows 10, la aplicación no se modifica y se seguirá ejecutando en modo de usuario de plena confianza.

## <a name="msix-containerization"></a>Creación de contenedores MSIX

Una nueva opción para el empaquetado de aplicaciones es MSIX. MSIX usa la tecnología de creación de contenedores disponible en Windows y combina los mejores aspectos del empaquetado de MSI, UWP y Hacer clic y ejecutar. Con herramientas para migrar instaladores existentes como EXE, MSI, APPV y APPX directamente a MSIX, vemos que la creación de contenedores MSIX proporciona una ruta de acceso unificada para muchas de las tecnologías de instalación que se usan en la actualidad. En las versiones actuales de Windows se incluye soporte técnico para MSIX: cualquier dispositivo con Windows 10 RS5 o versiones posteriores incluye todo lo necesario para instalar y ejecutar aplicaciones empaquetadas con MSIX. Windows 10 integra de forma dinámica los contenedores MSIX que recibe, al tiempo que separa las aplicaciones del sistema operativo.

La creación de contenedores significa la desinstalación y eliminación limpia de los paquetes, a diferencia de muchos paquetes actuales basados en EXE y MSI que pueden dejar elementos en el sistema. También significa que solo se necesitan credenciales de usuario estándar para instalar las aplicaciones; no se necesitan credenciales de administrador para instalar contenedores MSIX. Los contenedores MSIX también son más eficientes de actualizar. Cuando se publica una actualización, el uso de diferencias de nivel de bloque significa que solo se aplican los archivos binarios nuevos, lo que reduce la carga de la actualización, para implementaciones más rápidas con menos ancho de banda de red.

Encontrará más información sobre MSIX en el [sitio Tech Community de MSIX](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX).

## <a name="next-step"></a>Siguiente paso

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[Paso 4: Archivos y configuración del usuario](https://aka.ms/mdd4)

## <a name="previous-step"></a>Paso anterior

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Paso 2: Preparación de los directorios y la red](https://aka.ms/mdd2) 