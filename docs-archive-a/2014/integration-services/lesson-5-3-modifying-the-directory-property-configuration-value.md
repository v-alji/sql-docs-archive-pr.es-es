---
title: 'Paso 3: Modificar el valor de configuración de la propiedad Directory | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ba2a091f-361c-4331-afe2-53b465164c36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a71a7a181322d60caca98da4ddf3261cbce99c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670428"
---
# <a name="step-3-modifying-the-directory-property-configuration-value"></a><span data-ttu-id="705f6-102">Paso 3: Modificación del valor de configuración de la propiedad Directory</span><span class="sxs-lookup"><span data-stu-id="705f6-102">Step 3: Modifying the Directory Property Configuration Value</span></span>
  <span data-ttu-id="705f6-103">En esta tarea, modificará el parámetro de configuración, almacenado en el archivo SSISTutorial.dtsConfig, para la propiedad Value de la variable de nivel de paquete `User::varFolderName`.</span><span class="sxs-lookup"><span data-stu-id="705f6-103">In this task, you will modify the configuration setting, stored in the SSISTutorial.dtsConfig file, for the Value property of the package-level variable `User::varFolderName`.</span></span> <span data-ttu-id="705f6-104">Esta variable actualiza la propiedad Directory del contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="705f6-104">The variable updates the Directory property of the Foreach Loop container.</span></span> <span data-ttu-id="705f6-105">El valor modificado apuntará a la `New Sample Data` carpeta que creó en la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="705f6-105">The modified value will point to the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="705f6-106">Una vez que haya modificado el parámetro de configuración y que haya ejecutado el paquete, la variable actualizará la propiedad Directory, mediante el valor rellenado desde el archivo de configuración, en lugar del valor del directorio configurado originalmente en el paquete.</span><span class="sxs-lookup"><span data-stu-id="705f6-106">After you modify the configuration setting and run the package, the Directory property will be updated by the variable, using the value populated from the configuration file instead of the directory value originally configured in the package.</span></span>  
  
### <a name="to-modify-the-configuration-setting-of-the-directory-property"></a><span data-ttu-id="705f6-107">Para modificar el parámetro de configuración de la propiedad Directory</span><span class="sxs-lookup"><span data-stu-id="705f6-107">To modify the configuration setting of the Directory property</span></span>  
  
1.  <span data-ttu-id="705f6-108">En el Bloc de notas o en cualquier editor de texto, busque y abra el archivo de configuración SSISTutorial.dtsConfig que ha creado utilizando el Asistente para la configuración de paquetes en la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="705f6-108">In Notepad or any other text editor, locate and open the SSISTutorial.dtsConfig configuration file that you created by using the Package Configuration Wizard in the previous task.</span></span>  
  
2.  <span data-ttu-id="705f6-109">Cambie el valor del elemento **ConfiguredValue** para que coincida con la ruta de acceso de la `New Sample Data` carpeta que creó en la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="705f6-109">Change the value of the **ConfiguredValue** element to match the path of the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="705f6-110">No especifique la ruta de acceso entre comillas.</span><span class="sxs-lookup"><span data-stu-id="705f6-110">Do not surround the path in quotes.</span></span> <span data-ttu-id="705f6-111">Si la `New Sample Data` carpeta se encuentra en el nivel raíz de la unidad (por ejemplo, C: \\ ), el XML actualizado debería ser similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="705f6-111">If the `New Sample Data` folder is at the root level of your drive (for example, C:\\), the updated XML should be similar to the following sample:</span></span>  
  
     `<?xml version="1.0"?><DTSConfiguration><DTSConfigurationHeading><DTSConfigurationFileInfo GeneratedBy="DOMAIN\UserName" GeneratedFromPackageName="Lesson 5" GeneratedFromPackageID="{F4475E73-59E3-478F-8EB2-B10AFA61D3FA}" GeneratedDate="6/10/2012 8:16:50 AM"/></DTSConfigurationHeading><Configuration ConfiguredType="Property" Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"><ConfiguredValue></ConfiguredValue></Configuration></DTSConfiguration>`  
  
     <span data-ttu-id="705f6-112">La información del encabezado,, `GeneratedBy` `GeneratedFromPackageID` y **GeneratedDate** será diferente en el archivo, por supuesto.</span><span class="sxs-lookup"><span data-stu-id="705f6-112">The heading information, `GeneratedBy`, `GeneratedFromPackageID`, and **GeneratedDate** will be different in your file, of course.</span></span> <span data-ttu-id="705f6-113">El elemento que debe observar es `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="705f6-113">The element to note is the `Configuration` element.</span></span> <span data-ttu-id="705f6-114">La propiedad `Value` de la variable `User::varFolderName` ahora contiene C:\New Sample Data.</span><span class="sxs-lookup"><span data-stu-id="705f6-114">The `Value` property of the variable, `User::varFolderName`, now contains C:\New Sample Data.</span></span>  
  
3.  <span data-ttu-id="705f6-115">Guarde el cambio y cierre el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="705f6-115">Save the change, and then close the text editor.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="705f6-116">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="705f6-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="705f6-117">Paso 4: Prueba del paquete del tutorial de la lección 5</span><span class="sxs-lookup"><span data-stu-id="705f6-117">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](../integration-services/lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
  
