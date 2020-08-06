---
title: Crear un proyecto de Visual C# SMO en Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Visual C# [SMO]
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
author: stevestein
ms.author: sstein
ms.openlocfilehash: b78820fafd37675332e6703cabbb87e78bde5864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674759"
---
# <a name="create-a-visual-c-smo-project-in-visual-studio-net"></a><span data-ttu-id="6e049-102">Crear un proyecto de Visual C# SMO en Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="6e049-102">Create a Visual C# SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="6e049-103">En esta sección se describe cómo generar una aplicación de consola SMO simple.</span><span class="sxs-lookup"><span data-stu-id="6e049-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="6e049-104">En este ejemplo se importan espacios de nombres, lo que habilita al programa para que haga referencia a los tipos SMO.</span><span class="sxs-lookup"><span data-stu-id="6e049-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="6e049-105">La importación del espacio de nombres `Agent` es opcional.</span><span class="sxs-lookup"><span data-stu-id="6e049-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="6e049-106">Úselo cuando esté escribiendo un programa que use el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente.</span><span class="sxs-lookup"><span data-stu-id="6e049-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="6e049-107">El espacio de nombres `Common` se requiere para establecer una conexión segura a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e049-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6e049-108">El espacio de nombres `SqlClient` se utiliza para procesar los errores de excepción de SQL.</span><span class="sxs-lookup"><span data-stu-id="6e049-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-c-smo-project-in-visual-studionet"></a><span data-ttu-id="6e049-109">Crear un proyecto de Visual C# SMO en Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="6e049-109">Creating a Visual C# SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="6e049-110">Inicie [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (o [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6e049-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="6e049-111">En el menú **Archivo**, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6e049-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="6e049-112">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="6e049-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="6e049-113">En el cuadro de diálogo **tipos de proyecto** , seleccione **Visual C#** y, a continuación, seleccione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="6e049-113">In **Project Types** dialog box, select **Visual C#**, and then select **Windows**.</span></span> <span data-ttu-id="6e049-114">En el [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] panel Plantillas instaladas, seleccione **aplicación para Windows**.</span><span class="sxs-lookup"><span data-stu-id="6e049-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Windows Application**.</span></span>  
  
4.  <span data-ttu-id="6e049-115">Opta En el campo **nombre** , escriba el nombre de la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e049-115">(Optional) In the **Name** field, type the name of the new application</span></span>  
  
5.  <span data-ttu-id="6e049-116">Seleccione el tipo de aplicación de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="6e049-116">Select the Visual C# application type.</span></span> <span data-ttu-id="6e049-117">En los ejemplos siguientes, seleccione **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="6e049-117">For the examples that follow, select **Console Application**.</span></span>  
  
6.  <span data-ttu-id="6e049-118">En el menú **Proyecto**, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="6e049-118">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="6e049-119">Aparecerá el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="6e049-119">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="6e049-120">Haga clic en **examinar**, busque los ensamblados SMO en la [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] carpeta y, a continuación, seleccione los archivos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6e049-120">Click **Browse**, locate the SMO assemblies in the [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] folder, and then select the following files.</span></span> <span data-ttu-id="6e049-121">Son los archivos mínimos necesarios para generar una aplicación SMO:</span><span class="sxs-lookup"><span data-stu-id="6e049-121">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="6e049-122">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="6e049-122">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="6e049-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="6e049-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="6e049-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="6e049-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
     <span data-ttu-id="6e049-125">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="6e049-125">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6e049-126">Utilice la tecla `Ctrl` para seleccionar más de un archivo.</span><span class="sxs-lookup"><span data-stu-id="6e049-126">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="6e049-127">Agregue cualquier ensamblado SMO adicional que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6e049-127">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="6e049-128">Por ejemplo, si está programando específicamente [!INCLUDE[ssSB](../../includes/sssb-md.md)], agregue los ensamblados siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e049-128">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="6e049-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="6e049-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="6e049-130">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6e049-130">Click **Open**.</span></span>  
  
10. <span data-ttu-id="6e049-131">En el menú **Ver** , haga clic en **código**.-o bien, seleccione las ventanas Program1.CS [diseño] y haga doble clic en Windows Forms para mostrar la ventana de código.</span><span class="sxs-lookup"><span data-stu-id="6e049-131">On the **View** menu, click **Code**.-Or-Select the Program1.cs [Design] Windows and double-click the windows form to show the code window.</span></span>  
  
11. <span data-ttu-id="6e049-132">En el código, antes de la instrucción de espacio de nombres, escriba las instrucciones `using` siguientes para certificar los tipos en el espacio de nombres de SMO:</span><span class="sxs-lookup"><span data-stu-id="6e049-132">In the code, before the namespace statement, type the following `using` statements to qualify the types in the SMO namespace:</span></span>  
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
12. <span data-ttu-id="6e049-133">SMO cuenta con varios espacios de nombres bajo Microsoft.SqlServer.Management.Smo, como Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="6e049-133">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="6e049-134">Agregue los espacios de nombres que sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="6e049-134">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="6e049-135">Ahora puede agregar su código SMO.</span><span class="sxs-lookup"><span data-stu-id="6e049-135">You can now add your SMO code.</span></span>  
  
  
