---
title: 'Lección 2: agregar bucles | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 01f2ed61-1e5a-4ec6-b6a6-2bd070c64077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65efb84b4e50b470470e396bbe5681ce4b5dfac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670432"
---
# <a name="lesson-2-adding-looping"></a><span data-ttu-id="57d37-102">Lección 2: Adición de bucles</span><span class="sxs-lookup"><span data-stu-id="57d37-102">Lesson 2: Adding Looping</span></span>
  <span data-ttu-id="57d37-103">En [la lección 1: crear el proyecto y el paquete básico](lesson-1-create-a-project-and-basic-package-with-ssis.md), creó un paquete que extrajo datos de un único origen de archivo plano, transformó los datos mediante transformaciones de búsqueda y, por último, cargó los datos en la tabla de hechos **FactCurrency** de la base de datos de ejemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="57d37-103">In [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md), you created a package that extracted data from a single flat file source, transformed the data using Lookup transformations, and finally loaded the data into the **FactCurrency** fact table of the **AdventureWorksDW2012** sample database.</span></span>  
  
 <span data-ttu-id="57d37-104">No obstante, no es muy habitual utilizar un solo archivo plano para el proceso de extracción, transformación y carga (ETL).</span><span class="sxs-lookup"><span data-stu-id="57d37-104">However, it is rare for an extract, transform, and load (ETL) process to use a single flat file.</span></span> <span data-ttu-id="57d37-105">Un proceso ETL típico utilizaría datos extraídos de varios orígenes de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="57d37-105">A typical ETL process would extract data from multiple flat file sources.</span></span> <span data-ttu-id="57d37-106">Para extraer datos de varios orígenes, se requiere un flujo de control iterativo.</span><span class="sxs-lookup"><span data-stu-id="57d37-106">Extracting data from multiple sources requires an iterative control flow.</span></span> <span data-ttu-id="57d37-107">Una de las características más esperadas de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] es la capacidad de agregar fácilmente una iteración o un bucle a los paquetes.</span><span class="sxs-lookup"><span data-stu-id="57d37-107">One of the most anticipated features of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is the ability to easily add iteration or looping to packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="57d37-108">proporciona dos tipos de contenedores para crear bucles en los paquetes: el contenedor de bucles Foreach y el contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="57d37-108">provides two types of containers for looping through packages: the Foreach Loop container and the For Loop container.</span></span> <span data-ttu-id="57d37-109">El contenedor de bucles Foreach usa un enumerador para crear el bucle, mientras que el contenedor de bucles For suele emplear una expresión variable.</span><span class="sxs-lookup"><span data-stu-id="57d37-109">The Foreach Loop container uses an enumerator to perform the looping, whereas the For Loop container typically uses a variable expression.</span></span> <span data-ttu-id="57d37-110">En esta lección se utiliza el contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="57d37-110">This lesson uses the Foreach Loop container.</span></span>  
  
 <span data-ttu-id="57d37-111">El contenedor de bucles Foreach permite que un paquete repita el flujo de control para cada miembro de un enumerador determinado.</span><span class="sxs-lookup"><span data-stu-id="57d37-111">The Foreach Loop container enables a package to repeat the control flow for each member of a specified enumerator.</span></span> <span data-ttu-id="57d37-112">Con el contenedor de bucles Foreach puede enumerar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57d37-112">With the Foreach Loop container, you can enumerate:</span></span>  
  
-   <span data-ttu-id="57d37-113">Filas de conjuntos de registros ADO</span><span class="sxs-lookup"><span data-stu-id="57d37-113">ADO recordset rows</span></span>  
  
-   <span data-ttu-id="57d37-114">Información del esquema de ADO .Net</span><span class="sxs-lookup"><span data-stu-id="57d37-114">ADO .Net schema information</span></span>  
  
-   <span data-ttu-id="57d37-115">Estructuras de archivos y directorios</span><span class="sxs-lookup"><span data-stu-id="57d37-115">File and directory structures</span></span>  
  
-   <span data-ttu-id="57d37-116">Variables del sistema, de paquete y de usuario</span><span class="sxs-lookup"><span data-stu-id="57d37-116">System, package and user variables</span></span>  
  
-   <span data-ttu-id="57d37-117">Objetos enumerables contenidos en una variable</span><span class="sxs-lookup"><span data-stu-id="57d37-117">Enumerable objects contained in a variable</span></span>  
  
-   <span data-ttu-id="57d37-118">Elementos de una colección</span><span class="sxs-lookup"><span data-stu-id="57d37-118">Items in a collection</span></span>  
  
-   <span data-ttu-id="57d37-119">Nodos de una expresión del lenguaje de rutas XML (XPath)</span><span class="sxs-lookup"><span data-stu-id="57d37-119">Nodes in an XML Path Language (XPath) expression</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="57d37-120">Objetos de administración (SMO)</span><span class="sxs-lookup"><span data-stu-id="57d37-120">Management Objects (SMO)</span></span>  
  
 <span data-ttu-id="57d37-121">En esta lección, modificará el paquete ETL simple creado en la lección 1 para beneficiarse del contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="57d37-121">In this lesson, you will modify the simple ETL package created in Lesson 1 to take advantage of the Foreach Loop container.</span></span> <span data-ttu-id="57d37-122">También establecerá variables de paquete definidas por el usuario para que el paquete del tutorial pueda iterarse en todos los archivos planos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="57d37-122">You will also set user-defined package variables to enable the tutorial package to iterate through all the flat files in the folder.</span></span> <span data-ttu-id="57d37-123">Si no ha finalizado la lección anterior, también puede copiar el paquete de la lección 1 finalizada incluido en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="57d37-123">If you have not completed the previous lesson, you can also copy the completed Lesson 1 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="57d37-124">En esta lección, no modificará el flujo de datos, solamente modificará el flujo de control.</span><span class="sxs-lookup"><span data-stu-id="57d37-124">In this lesson, you will not modify the data flow, only the control flow.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="57d37-125">Para este tutorial, se necesita la base de datos de ejemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="57d37-125">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="57d37-126">Para obtener más información sobre cómo instalar e implementar **AdventureWorksDW2012**, vea [Ejemplos de productos de Reporting Services en CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="57d37-126">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="57d37-127">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="57d37-127">Lesson Tasks</span></span>  
 <span data-ttu-id="57d37-128">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="57d37-128">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="57d37-129">Paso 1: Copia del paquete de la lección 1</span><span class="sxs-lookup"><span data-stu-id="57d37-129">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
-   [<span data-ttu-id="57d37-130">Paso 2: Adición y configuración del contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="57d37-130">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
-   [<span data-ttu-id="57d37-131">Paso 3: Modificación del Administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="57d37-131">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="57d37-132">Paso 4: Prueba del paquete del tutorial de la lección 2</span><span class="sxs-lookup"><span data-stu-id="57d37-132">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="57d37-133">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="57d37-133">Start the Lesson</span></span>  
 [<span data-ttu-id="57d37-134">Paso 1: Copia del paquete de la lección 1</span><span class="sxs-lookup"><span data-stu-id="57d37-134">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="57d37-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57d37-135">See Also</span></span>  
 [<span data-ttu-id="57d37-136">Contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="57d37-136">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
