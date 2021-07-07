---
title: Usar Microsoft OneDrive Learning tools Interoperability
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Cree y cale las asignaciones, cree y cura el contenido del curso y colabore en archivos en tiempo real con la nueva aplicación de interoperabilidad Microsoft OneDrive Learning Tools.
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322226"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="d483d-103">Integrar Microsoft OneDrive LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="d483d-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="d483d-104">La integración Microsoft OneDrive LTI con Canvas es un proceso de dos pasos.</span><span class="sxs-lookup"><span data-stu-id="d483d-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="d483d-105">El primer paso habilita Microsoft OneDrive canvas y el segundo paso hace que el Microsoft OneDrive LTI esté disponible en los cursos de Canvas.</span><span class="sxs-lookup"><span data-stu-id="d483d-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="d483d-106">Configuración recomendada del explorador</span><span class="sxs-lookup"><span data-stu-id="d483d-106">Recommended browser settings</span></span>

- <span data-ttu-id="d483d-107">Las cookies deben estar habilitadas para Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d483d-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="d483d-108">Los elementos emergentes no deben bloquearse Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d483d-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="d483d-109">Las cookies no están habilitadas de forma predeterminada en el modo de incógnito del explorador Chrome y tendrán que estar habilitadas.</span><span class="sxs-lookup"><span data-stu-id="d483d-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="d483d-110">Microsoft OneDrive LTI funciona en modo privado en Microsoft Edge explorador.</span><span class="sxs-lookup"><span data-stu-id="d483d-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="d483d-111">Asegúrese de que no ha bloqueado las cookies (que están habilitadas de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="d483d-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="d483d-112">Habilitar Microsoft OneDrive LTI en canvas</span><span class="sxs-lookup"><span data-stu-id="d483d-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d483d-113">La persona que realiza esta integración debe ser un administrador de Canvas y un administrador del Microsoft 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="d483d-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="d483d-114">Inicie sesión en el <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive de registro de LTI</a></span><span class="sxs-lookup"><span data-stu-id="d483d-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="d483d-115">Seleccione el **botón Consentimiento de** administrador y acepte los permisos.</span><span class="sxs-lookup"><span data-stu-id="d483d-115">Select the **Admin Consent** button and accept the permissions.</span></span>

> [!CAUTION]
> <span data-ttu-id="d483d-116">Si este paso no se realiza, el siguiente paso le dará un error y no podrá realizar este paso durante una hora una vez que haya recibido el error.</span><span class="sxs-lookup"><span data-stu-id="d483d-116">If this step isn't performed, the following step will give you an error, and you won't be able to take this step for an hour once you've gotten the error.</span></span>

3. <span data-ttu-id="d483d-117">Seleccione el **botón Crear nuevo inquilino de LTI.**</span><span class="sxs-lookup"><span data-stu-id="d483d-117">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="d483d-118">En la página Registro de LTI, seleccione **Lienzo** en el desplegable y escriba la dirección URL base de la instancia de Canvas.</span><span class="sxs-lookup"><span data-stu-id="d483d-118">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="d483d-119">Si la instancia de Canvas es, por ejemplo, ]( , se debe especificar la https://contoso.test.instructure.com https://contoso.test.instructure.com) dirección URL completa.</span><span class="sxs-lookup"><span data-stu-id="d483d-119">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Página de administración de inquilinos de LTI, con un campo desplegable para elegir la plataforma de consumidor de LTI y un campo de texto de dirección URL.":::

4. <span data-ttu-id="d483d-121">Copie el JSON seleccionando el **botón Copiar** (un icono de la derecha que muestra dos páginas una encima de otra).</span><span class="sxs-lookup"><span data-stu-id="d483d-121">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="d483d-122">Se usará para generar la clave en Canvas.</span><span class="sxs-lookup"><span data-stu-id="d483d-122">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Imagen que muestra el botón copiar que copiará el texto JSON mostrado y lo hará disponible para la generación de claves en Canvas.":::

5. <span data-ttu-id="d483d-124">Inicie sesión en la instancia de Canvas como administrador y seleccione **Claves** de desarrollador en el menú de la parte izquierda de la página.</span><span class="sxs-lookup"><span data-stu-id="d483d-124">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="d483d-125">En el desplegable, crea una clave de desarrollador **seleccionando Clave LTI** en el desplegable de la parte superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="d483d-125">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Captura de pantalla que muestra la barra de navegación de la izquierda con las claves de desarrollador seleccionadas y la entrada de clave LTI seleccionada en un desplegable a la derecha de la página.":::

6. <span data-ttu-id="d483d-127">En la página Configurar, en el menú desplegable Método, seleccione Pegar **JSON** como método y pegue el texto JSON que copió en el paso 5 en el campo de texto que aparece. </span><span class="sxs-lookup"><span data-stu-id="d483d-127">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="d483d-128">Guarde la clave y estará disponible en Canvas en **estado Desactivado.**</span><span class="sxs-lookup"><span data-stu-id="d483d-128">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="d483d-129">Active la tecla **y** copie la clave especificada en la columna **Detalles** que se usará en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="d483d-129">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="La página Canvas con la clave establecida en estado desactivado. Tendrá que estar activada y la clave tendrá que copiarse de la columna de detalles de esta página.":::

8. <span data-ttu-id="d483d-131">Vuelva al portal Microsoft OneDrive registro de LTI y pegue la clave en el campo **Identificador de cliente de** Canvas.</span><span class="sxs-lookup"><span data-stu-id="d483d-131">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="d483d-132">Seleccione **Siguiente** cuando esté listo.</span><span class="sxs-lookup"><span data-stu-id="d483d-132">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Página de registro de inquilino de LTI, que muestra el texto JSON y el cuadro de texto en el que se debe copiar la clave.":::

9. <span data-ttu-id="d483d-134">Revise y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="d483d-134">Review and save your changes.</span></span> <span data-ttu-id="d483d-135">Se mostrará un mensaje al registrarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="d483d-135">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="d483d-136">Los detalles de registro también se pueden revisar seleccionando el botón Ver **inquilinos de LTI** en la página principal.</span><span class="sxs-lookup"><span data-stu-id="d483d-136">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="d483d-137">Habilitar Microsoft OneDrive LTI en cursos de Canvas</span><span class="sxs-lookup"><span data-stu-id="d483d-137">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="d483d-138">Un administrador de Canvas puede habilitar Microsoft OneDrive LTI para todos los cursos.</span><span class="sxs-lookup"><span data-stu-id="d483d-138">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="d483d-139">Si Microsoft OneDrive LTI es necesario en un curso específico (y no en todos los cursos), el profesor del curso debe seguir los mismos pasos dentro de la configuración del curso.</span><span class="sxs-lookup"><span data-stu-id="d483d-139">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="d483d-140">Inicie sesión como administrador y vaya a la **Configuración.**</span><span class="sxs-lookup"><span data-stu-id="d483d-140">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="d483d-141">Ve a la **sección Aplicaciones** y selecciona el botón **Ver configuraciones de** aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d483d-141">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="d483d-142">Seleccione el **botón Agregar aplicación.**</span><span class="sxs-lookup"><span data-stu-id="d483d-142">Select the **Add App** button.</span></span>
4. <span data-ttu-id="d483d-143">En el **desplegable Tipo de configuración,** elija la **opción Por identificador de** cliente.</span><span class="sxs-lookup"><span data-stu-id="d483d-143">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="d483d-144">Pegue el valor de la clave de desarrollador generada anteriormente en el campo **Id.** de cliente y seleccione el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="d483d-144">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="La página Agregar aplicación, que muestra la opción Por identificador de cliente en el menú desplegable Tipo de configuración.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="d483d-146">Colaboración Configuración para Microsoft OneDrive LTI en cursos de lienzo</span><span class="sxs-lookup"><span data-stu-id="d483d-146">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="d483d-147">Para que la colaboración funcione para profesores y alumnos, no debe habilitar la configuración de colaboración.</span><span class="sxs-lookup"><span data-stu-id="d483d-147">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="d483d-148">Para asegurarse de que la configuración no está habilitada, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d483d-148">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="d483d-149">Inicie sesión como administrador y vaya a la **Configuración.**</span><span class="sxs-lookup"><span data-stu-id="d483d-149">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="d483d-150">Vaya a **la sección Opciones de** características y, a continuación, vaya a la **sección** Curso.</span><span class="sxs-lookup"><span data-stu-id="d483d-150">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="d483d-151">Establezca la **característica Herramienta de colaboraciones externas** para que no esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="d483d-151">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="d483d-152">La colaboración se puede asignar a alumnos individuales y grupos de alumnos.</span><span class="sxs-lookup"><span data-stu-id="d483d-152">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="d483d-153">La asignación a alumnos individuales funciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d483d-153">Assigning to individual students works by default.</span></span> <span data-ttu-id="d483d-154">Para poder asignar colaboración a un grupo de alumnos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d483d-154">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="d483d-155">Inicie sesión como administrador y vaya a la **sección Claves de** desarrollador.</span><span class="sxs-lookup"><span data-stu-id="d483d-155">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="d483d-156">Busque la clave con el valor 17000000000710 y estadóla en **On**.</span><span class="sxs-lookup"><span data-stu-id="d483d-156">Find the key with value 170000000000710 and set it to **On**.</span></span>
