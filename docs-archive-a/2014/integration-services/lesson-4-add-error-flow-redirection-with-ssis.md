---
title: 'Lección 4: agregar redirección de flujo de errores | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c8dbda2-75e3-4278-9b4e-dcd220c92522
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b1d1ff9abf59a6288d1b693fce5a6fb707a129b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750021"
---
# <a name="lesson-4-adding-error-flow-redirection"></a><span data-ttu-id="a1e85-102">Lección 4: Adición de redirección de flujo de errores</span><span class="sxs-lookup"><span data-stu-id="a1e85-102">Lesson 4: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="a1e85-103">Para controlar los errores que pueden producirse en el proceso de transformación, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ofrece la posibilidad de decidir por componente y por columna cómo administrar los datos que no se pueden transformar.</span><span class="sxs-lookup"><span data-stu-id="a1e85-103">To handle errors that may occur in the transformation process, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gives you the ability to decide on a per component and per column basis how to handle data that cannot be transformed.</span></span> <span data-ttu-id="a1e85-104">Puede optar por omitir un error en determinadas columnas, redireccionar toda la fila que ha generado el error o simplemente rechazar el componente debido a un error.</span><span class="sxs-lookup"><span data-stu-id="a1e85-104">You can choose to ignore a failure in certain columns, redirect the entire failed row, or just fail the component.</span></span> <span data-ttu-id="a1e85-105">De forma predeterminada, todos los componentes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] están configurados para ser rechazados si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="a1e85-105">By default, all components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are configured to fail when errors occur.</span></span> <span data-ttu-id="a1e85-106">Rechazar el componente debido a un error, causa, a su vez, que el paquete también genere un error y que todos los procesos subsiguientes se detengan.</span><span class="sxs-lookup"><span data-stu-id="a1e85-106">Failing a component, in turn, causes the package to fail and all subsequent processing to stop.</span></span>  
  
 <span data-ttu-id="a1e85-107">En lugar de dejar que los errores detengan la ejecución de los paquetes, es recomendable configurar y administrar los posibles errores de procesamiento como si se produjeran en la transformación.</span><span class="sxs-lookup"><span data-stu-id="a1e85-107">Instead of letting failures stop package execution, it is good practice to configure and handle potential processing errors as they occur within the transformation.</span></span> <span data-ttu-id="a1e85-108">Si bien puede optar por omitir los errores a fin de garantizar que el paquete se ejecute correctamente, generalmente es mejor redireccionar la fila que genera el error a otra ruta de proceso en la que los datos y el error puedan persistir, puedan examinarse y puedan procesarse de nuevo más adelante.</span><span class="sxs-lookup"><span data-stu-id="a1e85-108">While you might choose to ignore failures to ensure your package runs successfully, it is often better to redirect the failed row to another processing path where the data and the error can be persisted, examined and reprocessed at a later time.</span></span>  
  
 <span data-ttu-id="a1e85-109">En esta lección, creará una copia del paquete que ha desarrollado en la [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="a1e85-109">In this lesson, you will create a copy of the package that you developed in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span></span> <span data-ttu-id="a1e85-110">Trabajando con este paquete nuevo, creará una versión dañada de los archivos de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1e85-110">Working with this new package, you will create a corrupted version of one of the sample data files.</span></span> <span data-ttu-id="a1e85-111">El archivo dañado forzará la aparición de un error de proceso al ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="a1e85-111">The corrupted file will force a processing error to occur when you run the package.</span></span>  
  
 <span data-ttu-id="a1e85-112">Para administrar los datos del error, agregará y configurará un destino de archivo plano que escribirá en un archivo las filas que no puedan encontrar un valor de búsqueda en la transformación Lookup Currency Key.</span><span class="sxs-lookup"><span data-stu-id="a1e85-112">To handle the error data, you will add and configure a Flat File destination that will write any rows that fail to locate a lookup value in the Lookup Currency Key transformation to a file.</span></span>  
  
 <span data-ttu-id="a1e85-113">Antes de escribir los datos del error en el archivo, incluirá un componente de script que utiliza un script para obtener descripciones de error.</span><span class="sxs-lookup"><span data-stu-id="a1e85-113">Before the error data is written to the file, you will include a Script component that uses script to get error descriptions.</span></span> <span data-ttu-id="a1e85-114">A continuación, volverá a configurar la transformación Lookup Currency Key para redireccionar los datos que no hayan podido procesarse en la transformación Script.</span><span class="sxs-lookup"><span data-stu-id="a1e85-114">You will then reconfigure the Lookup Currency Key transformation to redirect any data that could not be processed to the Script transformation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1e85-115">Para este tutorial, se necesita la base de datos de ejemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="a1e85-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="a1e85-116">Para obtener más información sobre cómo instalar e implementar **AdventureWorksDW2012**, consulte [Proyecto de ejemplo de productos de Reporting Services en CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span><span class="sxs-lookup"><span data-stu-id="a1e85-116">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples Project on CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span></span>  
  
## <a name="tasks-in-lesson"></a><span data-ttu-id="a1e85-117">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="a1e85-117">Tasks in Lesson</span></span>  
 <span data-ttu-id="a1e85-118">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a1e85-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="a1e85-119">Paso 1: Copia del paquete de la lección 3</span><span class="sxs-lookup"><span data-stu-id="a1e85-119">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
-   [<span data-ttu-id="a1e85-120">Paso 2: Creación de un archivo dañado</span><span class="sxs-lookup"><span data-stu-id="a1e85-120">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
-   [<span data-ttu-id="a1e85-121">Paso 3: Adición de redirección de flujo de errores</span><span class="sxs-lookup"><span data-stu-id="a1e85-121">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
-   [<span data-ttu-id="a1e85-122">Paso 4: Adición de un destino de archivo plano</span><span class="sxs-lookup"><span data-stu-id="a1e85-122">Step 4: Adding a Flat File Destination</span></span>](lesson-4-4-adding-a-flat-file-destination.md)  
  
-   [<span data-ttu-id="a1e85-123">Paso 5: Prueba del paquete del tutorial de la lección 4</span><span class="sxs-lookup"><span data-stu-id="a1e85-123">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="a1e85-124">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="a1e85-124">Start the Lesson</span></span>  
 [<span data-ttu-id="a1e85-125">Paso 1: Copia del paquete de la lección 3</span><span class="sxs-lookup"><span data-stu-id="a1e85-125">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
  
