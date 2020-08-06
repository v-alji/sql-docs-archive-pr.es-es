---
title: 'Paso 5: Agregar y configurar el origen de archivo plano | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c95ce51-e0fe-4fc5-95eb-2945929f2b13
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 504cfb4bc722627eb8ee70ec1f2c562cef8f1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673123"
---
# <a name="step-5-adding-and-configuring-the-flat-file-source"></a><span data-ttu-id="88a53-102">Paso 5: Adición y configuración del origen de archivo plano</span><span class="sxs-lookup"><span data-stu-id="88a53-102">Step 5: Adding and Configuring the Flat File Source</span></span>
  <span data-ttu-id="88a53-103">En esta tarea, agregará un origen de archivo plano al paquete y configurará dicho origen.</span><span class="sxs-lookup"><span data-stu-id="88a53-103">In this task, you will add and configure a Flat File source to your package.</span></span> <span data-ttu-id="88a53-104">Un origen de archivo plano es un componente de flujo de datos que utiliza metadatos definidos por un administrador de conexiones de archivo plano para especificar el formato y la estructura de los datos que deben extraerse del archivo plano mediante un proceso de transformación.</span><span class="sxs-lookup"><span data-stu-id="88a53-104">A Flat File source is a data flow component that uses metadata defined by a Flat File connection manager to specify the format and structure of the data to be extracted from the flat file by a transform process.</span></span> <span data-ttu-id="88a53-105">El origen de archivo plano puede configurarse para extraer datos de un único archivo plano utilizando la definición de formato de archivo proporcionada por el administrador de conexiones de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="88a53-105">The Flat File source can be configured to extract data from a single flat file by using the file format definition provided by the Flat File connection manager.</span></span>  
  
 <span data-ttu-id="88a53-106">En este tutorial, configurará el origen de archivo plano para utilizar el `Sample Flat File Source Data` Administrador de conexiones que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="88a53-106">For this tutorial, you will configure the Flat File source to use the `Sample Flat File Source Data` connection manager that you previously created.</span></span>  
  
### <a name="to-add-a-flat-file-source-component"></a><span data-ttu-id="88a53-107">Para agregar un componente de origen de archivo plano</span><span class="sxs-lookup"><span data-stu-id="88a53-107">To add a Flat File Source component</span></span>  
  
1.  <span data-ttu-id="88a53-108">Abra el diseñador de **flujo de datos** ; para ello, haga doble clic en la `Extract Sample Currency Data` tarea flujo de datos o haga clic en la **pestaña flujo de datos**.</span><span class="sxs-lookup"><span data-stu-id="88a53-108">Open the **Data Flow** designer, either by double-clicking the `Extract Sample Currency Data` data flow task or by clicking the **Data Flow tab**.</span></span>  
  
2.  <span data-ttu-id="88a53-109">En el **cuadro de herramientas de SSIS**, expanda **Otros orígenes**y, después, arrastre un **Origen de archivo plano** a la superficie de diseño de la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="88a53-109">In the **SSIS Toolbox**, expand **OtherSources**, and then drag a **Flat File Source** onto the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="88a53-110">En la superficie de diseño **flujo de datos** , haga clic con el botón secundario en el **origen de archivo plano**que acaba de agregar, haga clic en cambiar **nombre**y cambie el nombre a `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="88a53-110">On the **Data Flow** design surface, right-click the newly added **Flat File Source**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
4.  <span data-ttu-id="88a53-111">Haga doble clic en el origen del archivo plano para abrir el cuadro de diálogo Editor de origen de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="88a53-111">Double-click the Flat File source to open the Flat File Source Editor dialog box.</span></span>  
  
5.  <span data-ttu-id="88a53-112">En el cuadro **Administrador de conexiones de archivos planos** , seleccione `Sample Flat File Source Data` .</span><span class="sxs-lookup"><span data-stu-id="88a53-112">In the **Flat file connection manager** box, select `Sample Flat File Source Data`.</span></span>  
  
6.  <span data-ttu-id="88a53-113">Haga clic en **Columnas** y compruebe que los nombres de las columnas son correctos.</span><span class="sxs-lookup"><span data-stu-id="88a53-113">Click **Columns** and verify that the names of the columns are correct.</span></span>  
  
7.  <span data-ttu-id="88a53-114">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="88a53-114">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="88a53-115">Haga clic con el botón derecho en el origen del archivo plano y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="88a53-115">Right-click the Flat File source and click **Properties**.</span></span>  
  
9. <span data-ttu-id="88a53-116">En el ventana Propiedades, compruebe que la `LocaleID` propiedad está establecida en **inglés (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="88a53-116">In the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="88a53-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="88a53-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="88a53-118">Paso 6: Adición y configuración de transformaciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="88a53-118">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="88a53-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88a53-119">See Also</span></span>  
 <span data-ttu-id="88a53-120">[Origen de archivo plano](data-flow/flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="88a53-120">[Flat File Source](data-flow/flat-file-source.md) </span></span>  
 [<span data-ttu-id="88a53-121">Editor del administrador de conexiones de archivos planos &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="88a53-121">Flat File Connection Manager Editor &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
  
