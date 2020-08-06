---
title: Creación de un proyecto de Visual Basic SMO en Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic [SMO]
ms.assetid: d7a3892c-0f1c-4c4d-8480-b58dce3720bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 844d27ab6aadbc972c6282c79adb13e15d55c322
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751445"
---
# <a name="create-a-visual-basic-smo-project-in-visual-studio-net"></a><span data-ttu-id="dc7aa-102">Crear un proyecto de Visual Basic SMO en Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="dc7aa-102">Create a Visual Basic SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="dc7aa-103">En esta sección se describe cómo generar una aplicación de consola SMO simple.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="dc7aa-104">En este ejemplo se importan espacios de nombres, lo que habilita al programa para que haga referencia a los tipos SMO.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="dc7aa-105">La importación del espacio de nombres `Agent` es opcional.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="dc7aa-106">Úselo cuando esté escribiendo un programa que use el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="dc7aa-107">El espacio de nombres `Common` se requiere para establecer una conexión segura a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc7aa-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dc7aa-108">El espacio de nombres `SqlClient` se utiliza para procesar los errores de excepción de SQL.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-basic-smo-project-in-visual-studionet"></a><span data-ttu-id="dc7aa-109">Crear un proyecto de Visual Basic SMO en Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="dc7aa-109">Creating a Visual Basic SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="dc7aa-110">Inicie [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (o [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="dc7aa-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="dc7aa-111">En el menú **Archivo**, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="dc7aa-112">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="dc7aa-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="dc7aa-113">En el cuadro de diálogo **tipos de proyecto** , seleccione **Visual Basic**y, a continuación, seleccione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-113">In **Project Types** dialog box, select **Visual Basic**, and then select **Windows**.</span></span> <span data-ttu-id="dc7aa-114">En el [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] panel Plantillas instaladas, seleccione **aplicación de consola.**</span><span class="sxs-lookup"><span data-stu-id="dc7aa-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Console Application.**</span></span>  
  
4.  <span data-ttu-id="dc7aa-115">Opta En el campo **nombre** , escriba el nombre de la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-115">(Optional) In the **Name** field, type the name of the new application.</span></span>  
  
5.  <span data-ttu-id="dc7aa-116">Haga clic en **Aceptar** para cargar la [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] plantilla de aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-116">Click **OK** to load the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] console application template.</span></span>  
  
6.  <span data-ttu-id="dc7aa-117">En el menú **Proyecto**, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-117">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="dc7aa-118">Aparecerá el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-118">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="dc7aa-119">Haga clic en **examinar**, busque los ensamblados SMO en la carpeta C:\Archivos de Programa\microsoft SQL Server\120\SDK\Assemblies y, a continuación, seleccione los archivos siguientes.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-119">Click **Browse**, locate the SMO assemblies in the C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies folder, and then select the following files.</span></span> <span data-ttu-id="dc7aa-120">Son los archivos mínimos necesarios para generar una aplicación SMO:</span><span class="sxs-lookup"><span data-stu-id="dc7aa-120">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="dc7aa-121">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="dc7aa-121">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="dc7aa-122">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="dc7aa-122">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
     <span data-ttu-id="dc7aa-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="dc7aa-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="dc7aa-124">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="dc7aa-124">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc7aa-125">Utilice la tecla `Ctrl` para seleccionar más de un archivo.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-125">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="dc7aa-126">Agregue cualquier ensamblado SMO adicional que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-126">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="dc7aa-127">Por ejemplo, si está programando específicamente [!INCLUDE[ssSB](../../includes/sssb-md.md)], agregue los ensamblados siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc7aa-127">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="dc7aa-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="dc7aa-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="dc7aa-129">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-129">Click **Open**.</span></span>  
  
10. <span data-ttu-id="dc7aa-130">En el menú **Ver** , haga clic en **código**. o bien seleccione la ventana Module1. VB para mostrar la ventana de código.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-130">On the **View** menu, click **Code**.-Or-Select the Module1.vb window to show the code window.</span></span>  
  
11. <span data-ttu-id="dc7aa-131">En el código, antes de cualquier declaración, escriba las instrucciones **Imports** siguientes para certificar los tipos en el espacio de nombres de SMO.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-131">In the code, before any declarations, type the following **Imports** statements to qualify the types in the SMO namespace.</span></span>  
  
    ```  
    Imports Microsoft.SqlServer.Management.Smo  
    Imports Microsoft.SqlServer.Management.Common  
    ```  
  
12. <span data-ttu-id="dc7aa-132">SMO cuenta con varios espacios de nombres bajo Microsoft.SqlServer.Management.Smo, como Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-132">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="dc7aa-133">Agregue los espacios de nombres que sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-133">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="dc7aa-134">Ahora puede agregar su código SMO.</span><span class="sxs-lookup"><span data-stu-id="dc7aa-134">You can now add your SMO code.</span></span>  
  
  
