---
title: Depurar procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- debugging stored procedures [Analysis Services]
- stored procedures [Analysis Services], debugging
ms.assetid: 34f51b85-02b3-40dd-bf93-375a9e522385
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4f5971fe611f06a413ca48b2bc91237a8c87ee8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746039"
---
# <a name="debugging-stored-procedures"></a><span data-ttu-id="5748b-102">Depurar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="5748b-102">Debugging Stored Procedures</span></span>
  <span data-ttu-id="5748b-103">Los procedimientos almacenados de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] son bibliotecas CLR o COM (generalmente DLL) escritas en C# (u otro lenguaje de bibliotecas CLR o COM).</span><span class="sxs-lookup"><span data-stu-id="5748b-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures are actually CLR or COM libraries (normally DLLs) that are written in C# (or any other CLR or COM language).</span></span> <span data-ttu-id="5748b-104">Por consiguiente, la depuración de un procedimiento almacenado es muy similar a la depuración de cualquier otra aplicación del entorno de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5748b-104">Therefore, debugging a stored procedure is much like debugging any other application in the Visual Studio debugging environment.</span></span> <span data-ttu-id="5748b-105">Los procedimientos almacenados del entorno de desarrollo de Visual Studio pueden depurarse con las funciones de depuración integradas.</span><span class="sxs-lookup"><span data-stu-id="5748b-105">You debug stored procedures in the Visual Studio development environment using the integrated debugging functions.</span></span> <span data-ttu-id="5748b-106">Con ellas podrá detenerse en ubicaciones de procedimientos, inspeccionar los valores de memoria y registro, cambiar variables, observar el tráfico de mensajes y examinar cómo funciona el código.</span><span class="sxs-lookup"><span data-stu-id="5748b-106">These allow you to stop at procedure locations, inspect memory and register values, change variables, observe message traffic and get a close look at how your code works.</span></span>  
  
### <a name="to-debug-a-stored-procedure"></a><span data-ttu-id="5748b-107">Para depurar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="5748b-107">To debug a stored procedure</span></span>  
  
1.  <span data-ttu-id="5748b-108">Abra el proyecto utilizado para crear la DLL en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5748b-108">Open the project used to create the DLL in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="5748b-109">Cree puntos de interrupción en el método o función correspondiente al procedimiento que desee depurar.</span><span class="sxs-lookup"><span data-stu-id="5748b-109">Create breakpoints in the method or function corresponding to the procedure you want to debug.</span></span>  
  
3.  <span data-ttu-id="5748b-110">Utilice Visual Studio para crear una compilación de depuración de una DLL del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="5748b-110">Use Visual Studio to create a debug build of a stored procedure DLL.</span></span>  
  
4.  <span data-ttu-id="5748b-111">Implemente la DLL en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5748b-111">Deploy the DLL to the server.</span></span> <span data-ttu-id="5748b-112">Para obtener más información acerca de cómo implementar el archivo DLL en el servidor, vea [crear procedimientos almacenados](creating-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5748b-112">For more information about deploying the DLL to the server, see [Creating Stored Procedures](creating-stored-procedures.md).</span></span>  
  
5.  <span data-ttu-id="5748b-113">Se necesita una aplicación que llame al procedimiento almacenado que desee probar.</span><span class="sxs-lookup"><span data-stu-id="5748b-113">You need an application that calls the stored procedure that you want to test.</span></span> <span data-ttu-id="5748b-114">Si no dispone de una, puede utilizar el Editor de consultas MDX de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para crear una consulta MDX que llame al procedimiento almacenado que desee probar.</span><span class="sxs-lookup"><span data-stu-id="5748b-114">If you do not have one ready, you can use the MDX Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create an MDX query that calls the stored procedure that you want to test.</span></span>  
  
6.  <span data-ttu-id="5748b-115">En Visual Studio, adjunte al proceso de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (Msmdsrv.exe).</span><span class="sxs-lookup"><span data-stu-id="5748b-115">In Visual Studio, attach to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process (Msmdsrv.exe).</span></span>  
  
    1.  <span data-ttu-id="5748b-116">En el menú **depurar** , elija **asociar toProcess**.</span><span class="sxs-lookup"><span data-stu-id="5748b-116">From the **Debug** menu, choose **Attatch toProcess**.</span></span>  
  
    2.  <span data-ttu-id="5748b-117">En el cuadro de diálogo **asociar toProcess** , seleccione **Mostrar procesos de todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5748b-117">In the **Attatch toProcess** dialog box, select **Show processes from all users**.</span></span>  
  
    3.  <span data-ttu-id="5748b-118">En la lista **procesos disponibles** , en la columna **proceso** , haga clic en **Msmdsrv.exe**.</span><span class="sxs-lookup"><span data-stu-id="5748b-118">In the **Available Processes** list, in the **Process** column, click **Msmdsrv.exe**.</span></span> <span data-ttu-id="5748b-119">Si se ejecutase más de una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el servidor, necesita identificar el proceso mediante el Id. de la instancia que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="5748b-119">If there is more than one instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] running on the server, you need to identify the process by the ID of the instance you want to use.</span></span>  
  
    4.  <span data-ttu-id="5748b-120">En el cuadro de texto **adjuntar a** , asegúrese de que está seleccionado el tipo de programa adecuado.</span><span class="sxs-lookup"><span data-stu-id="5748b-120">In the **Attach to** text box, make sure that the appropriate program type is selected.</span></span> <span data-ttu-id="5748b-121">Para un archivo DLL de CLR, haga clic en **seleccionar**, elija **depurar estos tipos de código**, haga clic en **administrado**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5748b-121">For a CLR DLL, click **Select**, then click **Debug these code types**, then click **Managed**, then click **OK**.</span></span> <span data-ttu-id="5748b-122">Para un archivo DLL COM, haga clic en **seleccionar**, elija **depurar estos tipos de código**, haga clic en **nativo**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5748b-122">For a COM DLL, click **Select**, then click **Debug these code types**, then click **Native**, then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="5748b-123">Haga clic en **Adjuntar**.</span><span class="sxs-lookup"><span data-stu-id="5748b-123">Click **Attach**.</span></span>  
  
7.  <span data-ttu-id="5748b-124">En [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], invoque el programa o el script MDX que llama al procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="5748b-124">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], invoke the program or MDX script that calls the stored procedure.</span></span> <span data-ttu-id="5748b-125">El depurador se interrumpirá al alcanzar una línea que contiene un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5748b-125">The debugger breaks when it reaches a line containing a breakpoint.</span></span> <span data-ttu-id="5748b-126">Podrá evaluar variables en la ventana de inspección, ver variables locales y reproducir el código.</span><span class="sxs-lookup"><span data-stu-id="5748b-126">You can evaluate variables in the watch window, view locals, and step through the code.</span></span>  
  
 <span data-ttu-id="5748b-127">Si experimenta problemas al depurar una biblioteca, compruebe que el archivo de la base de datos del programa (PDB) correspondiente se ha copiado en la ubicación de implementación del servidor.</span><span class="sxs-lookup"><span data-stu-id="5748b-127">If you have problems debugging a library, make sure that the corresponding program database (PDB) file was copied to the deployment location on the server.</span></span> <span data-ttu-id="5748b-128">Si no se ha copiado el archivo durante el registro o la implementación, es necesario copiarlo manualmente en la misma ubicación que la DLL.</span><span class="sxs-lookup"><span data-stu-id="5748b-128">If this file was not copied during registration or deployment, you must copy it manually to the same location as the DLL.</span></span> <span data-ttu-id="5748b-129">En el código nativo (DLL de COM), el archivo PDB reside en el subdirectorio \debug.</span><span class="sxs-lookup"><span data-stu-id="5748b-129">For native code (COM DLL), the PDB file resides in the \debug subdirectory.</span></span> <span data-ttu-id="5748b-130">En el código administrado (DLL de CLR), reside en el subdirectorio \WINDEBUG.</span><span class="sxs-lookup"><span data-stu-id="5748b-130">For managed code (CLR DLL), it resides in the \WINDEBUG subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5748b-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5748b-131">See Also</span></span>  
 <span data-ttu-id="5748b-132">[Administración de ensamblados de modelos multidimensionales](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="5748b-132">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="5748b-133">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="5748b-133">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
