---
title: 'Paso 2: Crear un archivo dañado | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd5fbe942774192881489e9ea430672f9da5083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672170"
---
# <a name="step-2-creating-a-corrupted-file"></a><span data-ttu-id="f06bf-102">Paso 2: Creación de un archivo dañado</span><span class="sxs-lookup"><span data-stu-id="f06bf-102">Step 2: Creating a Corrupted File</span></span>
  <span data-ttu-id="f06bf-103">Para demostrar los errores de configuración y el control de los errores de transformación, debe crear un archivo plano de ejemplo que, cuando se procese, genere un error en un componente.</span><span class="sxs-lookup"><span data-stu-id="f06bf-103">In order to demonstrate the configuration and handling of transformation errors, you will have to create a sample flat file that when processed causes a component to fail.</span></span>  
  
 <span data-ttu-id="f06bf-104">En esta tarea, creará una copia de un archivo plano de ejemplo existente.</span><span class="sxs-lookup"><span data-stu-id="f06bf-104">In this task, you will create a copy of an existing sample flat file.</span></span> <span data-ttu-id="f06bf-105">Luego abrirá el archivo en el Bloc de notas y modificará la columna **CurrencyID** para garantizar que no pueda producir una coincidencia durante la búsqueda de transformaciones.</span><span class="sxs-lookup"><span data-stu-id="f06bf-105">You will then open the file in Notepad and edit the **CurrencyID** column to ensure that it will fail to produce a match during the transformations lookup.</span></span> <span data-ttu-id="f06bf-106">Cuando se procese el archivo nuevo, el error de búsqueda hará que se produzca un error en la transformación Lookup Currency Key y, por consiguiente, el resto del paquete generará un error.</span><span class="sxs-lookup"><span data-stu-id="f06bf-106">When the new file is processed, the lookup failure will cause the Currency Key Lookup transformation to fail and therefore fail the rest of the package.</span></span> <span data-ttu-id="f06bf-107">Una vez que haya creado el archivo de ejemplo dañado, ejecutará el paquete para ver su error.</span><span class="sxs-lookup"><span data-stu-id="f06bf-107">After you have created the corrupted sample file, you will run the package to view the package failure.</span></span>  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a><span data-ttu-id="f06bf-108">Para crear un archivo plano de ejemplo dañado</span><span class="sxs-lookup"><span data-stu-id="f06bf-108">To create a corrupted sample flat file</span></span>  
  
1.  <span data-ttu-id="f06bf-109">En el Bloc de notas o en cualquier otro editor de texto, abra el archivo Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="f06bf-109">In Notepad or any other text editor, open the Currency_VEB.txt file.</span></span>  
  
     <span data-ttu-id="f06bf-110">Los datos de ejemplo se incluyen con los paquetes de lecciones de SSIS.</span><span class="sxs-lookup"><span data-stu-id="f06bf-110">The sample data is included with the SSIS Lesson packages.</span></span> <span data-ttu-id="f06bf-111">Para descargar los datos de ejemplo y los paquetes de lecciones, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f06bf-111">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="f06bf-112">Vaya a [Integration Services ejemplos del producto](https://go.microsoft.com/fwlink/?LinkID=267527).</span><span class="sxs-lookup"><span data-stu-id="f06bf-112">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span></span>  
  
    2.  <span data-ttu-id="f06bf-113">Haga clic en la pestaña **descargas** .</span><span class="sxs-lookup"><span data-stu-id="f06bf-113">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="f06bf-114">Haga clic en el archivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="f06bf-114">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
2.  <span data-ttu-id="f06bf-115">Use la característica buscar y reemplazar del editor de texto para buscar todas las instancias de `VEB` y reemplazarlas por `BAD` .</span><span class="sxs-lookup"><span data-stu-id="f06bf-115">Use the text editor's find and replace feature to find all instances of `VEB` and replace them with `BAD`.</span></span>  
  
3.  <span data-ttu-id="f06bf-116">En la misma carpeta que los demás archivos de datos de ejemplo, guarde el archivo modificado como `Currency_BAD.txt` .</span><span class="sxs-lookup"><span data-stu-id="f06bf-116">In the same folder as the other sample data files, save the modified file as `Currency_BAD.txt`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f06bf-117">Asegúrese de que `Currency_BAD.txt` está guardado en la misma carpeta que los demás archivos de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f06bf-117">Make sure that `Currency_BAD.txt` is saved the same folder as the other sample data files.</span></span>  
  
4.  <span data-ttu-id="f06bf-118">Cierre el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f06bf-118">Close your text editor.</span></span>  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a><span data-ttu-id="f06bf-119">Para comprobar que se producirá un error durante la ejecución</span><span class="sxs-lookup"><span data-stu-id="f06bf-119">To verify that an error will occur during run time</span></span>  
  
1.  <span data-ttu-id="f06bf-120">En el menú **Depurar**, haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="f06bf-120">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="f06bf-121">En la tercera iteración del flujo de datos, la transformación Lookup Currency Key intenta procesar el archivo Currency_BAD.txt y la transformación generará un error.</span><span class="sxs-lookup"><span data-stu-id="f06bf-121">On the third iteration of the data flow, the Lookup Currency Key transformation tries to process the Currency_BAD.txt file, and the transformation will fail.</span></span> <span data-ttu-id="f06bf-122">El error de la transformación hará que todo el paquete genere un error.</span><span class="sxs-lookup"><span data-stu-id="f06bf-122">The failure of the transformation will cause the whole package to fail.</span></span>  
  
2.  <span data-ttu-id="f06bf-123">En el menú **Depurar**, haga clic en **Detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="f06bf-123">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
3.  <span data-ttu-id="f06bf-124">En la superficie de diseño, haga clic en la pestaña **Resultados de la ejecución** .</span><span class="sxs-lookup"><span data-stu-id="f06bf-124">On the design surface, click the **Execution Results** tab.</span></span>  
  
4.  <span data-ttu-id="f06bf-125">Examine el registro y compruebe que se ha producido el siguiente error no controlado:</span><span class="sxs-lookup"><span data-stu-id="f06bf-125">Browse through the log and verify that the following unhandled error occurred:</span></span>  
  
     `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    >  <span data-ttu-id="f06bf-126">El número 27 es el Id. del componente.</span><span class="sxs-lookup"><span data-stu-id="f06bf-126">The number 27 is the ID of the component.</span></span> <span data-ttu-id="f06bf-127">Este valor se asigna al generar el flujo de datos, y es posible que el valor del paquete sea diferente.</span><span class="sxs-lookup"><span data-stu-id="f06bf-127">This value is assigned when you build the data flow, and the value in your package may be different.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f06bf-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f06bf-128">Next Steps</span></span>  
 [<span data-ttu-id="f06bf-129">Paso 3: Adición de redirección de flujo de errores</span><span class="sxs-lookup"><span data-stu-id="f06bf-129">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
  
